

describe方法将object转为map

导入
`import org.apache.commons.beanutils.PropertyUtils;`

```
@Test
    public void test2() throws IllegalAccessException, NoSuchMethodException, InvocationTargetException {
        Person person = new Person();
        person.setName("san");
        person.setSex("male");
        Map<String, Object> describe = PropertyUtils.describe(person);
        //{sex=male, name=san, class=class cn.wj.licode.Person}
        //System.out.println(describe);
        describe.remove("class");
        Map map = new HashMap();
        map.put("屁股","贼大");
        describe.putAll(map);
        //{sex=male, name=san, 屁股=贼大}
        System.out.println(describe);
    }
```

pom依赖:

```
 <!-- https://mvnrepository.com/artifact/commons-beanutils/commons-beanutils -->
        <dependency>
            <groupId>commons-beanutils</groupId>
            <artifactId>commons-beanutils</artifactId>
            <version>1.9.3</version>
        </dependency>
```

