# java中Element

构建XML中的节点

解析或生成xml文档都需要用到这个类。



```
        <!-- https://mvnrepository.com/artifact/org.dom4j/dom4j -->
        <dependency>
            <groupId>org.dom4j</groupId>
            <artifactId>dom4j</artifactId>
            <version>2.0.0</version>
        </dependency>

```

```
import org.dom4j.Document;
import org.dom4j.DocumentException;
import org.dom4j.DocumentHelper;
import org.dom4j.Element;

import java.util.Iterator;


public class ElementDemo {
    public static void main(String[] args) throws DocumentException {
        String xmlStr="<root><p>ni</p><a>test</a></root>";
        Document document =DocumentHelper.parseText(xmlStr);
        Element root = document.getRootElement();//获得根节点
        //迭代 :读取根节点下的所有节点
        for (Iterator<Element> i = root.elementIterator();i.hasNext();){
            Element element = i.next();
            System.out.println("节点名："+element.getName());
            System.out.println("值："+element.getData());
        }
        /**
         * 节点名：p
         * 值：ni
         * 节点名：a
         * 值：test
         * */
    }
}
```



新建

```
Document document=DocumentHelper.createDocument();
        //创建根结点
        Element root=document.addElement("root");
        //为根结点添加一个book节点
        Element book1=root.addElement("book");
        //为book1添加属性type
        book1.addAttribute("type","science");
        //为book1添加name子节点
        Element name1=book1.addElement("Name");
        //并设置其name为"Java"
        name1.setText("Java");
        //为book1创建一个price节点,并设其价格为100
        book1.addElement("price").setText("100");

        //为根结点添加第二个book节点，并设置该book节点的type属性
        Element book2=root.addElement("book").addAttribute("type","science");
        //为book1添加name子节点
        Element name2=book2.addElement("Name");
        //并设置其name为"Oracle"
        name2.setText("Oracle");
        //为book1创建一个price节点,并设其价格为200
        book2.addElement("price").setText("200");

        //输出xml
        System.out.println(document.asXML());
        
       
  //<?xml version="1.0" encoding="UTF-8"?>
		<root><book type="science"><Name>Java</Name><price>100</price></book><book 					type="science"><Name>Oracle</Name><price>200</price></book></root>

```

