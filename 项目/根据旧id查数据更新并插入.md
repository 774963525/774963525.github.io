需求:新系统code与老系统中的code不匹配,根据中间表找到老表中的数据,复制一份后将code改为新code,注意可能出现新code对应多条老code情况,需要合并老code数据

```
/**
	 * 合并对象相同Subtype,去重并合并Numpages
	 * */
	private List<EsDocMain> getNewList(List<EsDocMain> newEsDocMains) {
		
		 HashMap<String,EsDocMain> tempMap = new HashMap<String,EsDocMain>();
	        //去掉重复的key
	        for(EsDocMain newEsDocMain : newEsDocMains){
	            String temp = newEsDocMain.getSubtype();
	            //containsKey(Object key)该方法判断Map集合中是否包含指定的键名，如果包含返回true，不包含返回false
	            //containsValue(Object value)该方法判断Map集合中是否包含指定的键值，如果包含返回true，不包含返回false
	            if(tempMap.containsKey(temp)){
	                EsDocMain newestEsDocMain = new EsDocMain();
	                newestEsDocMain.setSubtype(temp);
	                //合并相同key的value (numpages相加)
	                newestEsDocMain.setNumpages(tempMap.get(temp).getNumpages().add(newEsDocMain.getNumpages()));
	                newestEsDocMain.setBusstype(tempMap.get(temp).getBusstype());
	                newestEsDocMain.setScanoperator(tempMap.get(temp).getScanoperator());
	                newestEsDocMain.setDocflag(tempMap.get(temp).getDocflag());
	                //将合并后的docid放在p2中
	                newestEsDocMain.setP2(tempMap.get(temp).getDocid()+","+newEsDocMain.getDocid());
	                newestEsDocMain.setScanDate(new Date());
	                newestEsDocMain.setSystemNo(tempMap.get(temp).getSystemNo());
//	                newestEsDocMain.setDocid(null);
	                newestEsDocMain.setDoccode(tempMap.get(temp).getDoccode());
	                
	                //HashMap不允许key重复，当有key重复时，前面key对应的value值会被覆盖
	                tempMap.put(temp,newestEsDocMain );
	            }else{
	                tempMap.put(temp,newEsDocMain );
	            }
	        }
	      //遍历key 将value取出放入list中
	        List<EsDocMain> newList = new ArrayList<EsDocMain>();
	         
	        for(String temp:tempMap.keySet()){
	        	
	            newList.add(tempMap.get(temp));
	        }

	        return newList;
	}
```



```
public void insert(){
		int threadCount = 25;
		ExecutorService newFixedThreadPool = Executors.newFixedThreadPool(threadCount);
		int jobCount=50000;
		SqlParam sqlparam = new SqlParam();
		sqlparam.add("number", jobCount);	
		List<ContractTransferSingle> contractTransferSingles = contractTransferSingleDao.selectAll(sqlparam);
		if(contractTransferSingles.size()==0){
			logger.info("复制再插入任务已全部完成");
			return ;
		}
		logger.info("本次复制再插入任务申请数：" + contractTransferSingles.size());
		if(contractTransferSingles.size()<threadCount){
			threadCount = contractTransferSingles.size();
		}
		int threadRunCount = (int) Math.ceil((double) contractTransferSingles.size() / threadCount);
		System.out.println("线程数为:"+threadRunCount);
		logger.info("历史数据复制再插入线程数：" + threadCount);
		List<List<ContractTransferSingle>> singleThreadList = new ArrayList<List<ContractTransferSingle>>();
		for (int i = 0; i < contractTransferSingles.size(); i += threadRunCount) {
			 List<ContractTransferSingle> productList = contractTransferSingles.stream().skip(i).limit(threadRunCount)
					.collect(Collectors.toList());
			 singleThreadList.add(productList);
		}
		//singleThreadList 为每条线程执行的数据list 例: [[a, b], [c, d], [e, f]]
		if (singleThreadList != null && singleThreadList.size() > 0) {
//			ThreadPool threadPool = ThreadPoolCache.threadPoolMap.get(PBIZContants.THREADPOOL_TYPE_APPDATASYN);
			for (List<ContractTransferSingle> contractTransList : singleThreadList) {
				//执行多线程
				InsertThread insertThread = new InsertThread();
				insertThread.setContractTransferList(contractTransList);
				newFixedThreadPool.execute(insertThread);
//				threadPool.addTaskThread(insertThread);
			}
	
		}
	}
```



线程中无法使用@Resource以及@Autowired,由于spring的定义域的问题,自写一个BeanContext

```
@Component
public class BeanContext implements ApplicationContextAware {

    private static ApplicationContext applicationContext;

    public void setApplicationContext(ApplicationContext applicationContext) throws BeansException {
        BeanContext.applicationContext = applicationContext;
    }

    public static ApplicationContext getApplicationContext(){
        return applicationContext;
    }

    @SuppressWarnings("unchecked")
    public static <T> T getBean(String name) throws BeansException {
        return (T)applicationContext.getBean(name);
    }

    public static <T> T getBean(Class<T> clz) throws BeansException {
        return (T)applicationContext.getBean(clz);
    }
}

//使用:
ChangeToNewDocCode changeToNewDocCode = BeanContext.getApplicationContext().getBean(ChangeToNewDocCode.class);
```

例:

```
public class PersonCombine {
	public static void main(String[] args) {
		List<Person> personList = new ArrayList<Person>();
		Person p1 = new Person();
		//为Integer类型可直接输入数字
		p1.setName("张三");
		p1.setAge(12);
		p1.setSalary(3000.0);
		Person p2 = new Person();
		p2.setName("李四");
		p2.setAge(12);
		p2.setSalary(4000.0);
		Person p3 = new Person();
		p3.setName("张三");
		p3.setAge(12);
		p3.setSalary(7000.0);
		Person p4 = new Person();
		p4.setName("王五");
		p4.setAge(12);
		p4.setSalary(1000.0);
		personList.add(p1);
		personList.add(p2);
		personList.add(p3);
		personList.add(p4);
		getNewList(personList);
	}

	private static void getNewList(List<Person> personList) {
		Map<String ,Person > tempMap = new HashMap<>();
		for(Person person:personList){
			String tempName = person.getName();
			if(tempMap.containsKey(tempName)){
				Person newPerson = new Person();
				newPerson.setName(tempName);

				newPerson.setSalary(tempMap.get(tempName).getSalary()+
						person.getSalary());
				tempMap.put(tempName,newPerson);
			}else{
				tempMap.put(tempName,person);
			}
		}

		//拿出
		List<Person> newList = new ArrayList<>();
		for (String key:tempMap.keySet()){
			newList.add(tempMap.get(key));
		}
		System.out.println(newList);
	}


}
```

