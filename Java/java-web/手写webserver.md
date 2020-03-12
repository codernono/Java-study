## 反射

反射：把java中类中的各种结构（方法，属性，构造器，类名）映射成一个个的Java对象

***获取Class对象的三种方式***

- 对象.getClass()
- 类.class
- Class.forName("全限定类名")

## XML解析

SAX解析过程

1. 获取解析工厂

   ```java
   SAXParserFactory factory = SAXParserFactory.newInstance();
   ```

2. 从解析工厂获取解析器

   ```java
   SAXParser parser = factory.newSAXParser();
   ```

3. 编写处理器

   ```
   xxxHandler handler = new xxxHandler();
   ```

4. 加载文档，注册处理器

   ```
   parser
   	.parse(Thread.currentThread()
   	.getContextClassLoader()
   	.getResourceAsStream("xxxx.xml"), handler);
   ```

5. 获取数据

### Handler

```java
class WebHandler extends DefaultHandler {
    @Override
    public void startDocument() throws SAXException {
       
    }
    
    @Override
    public void startElement(String uri, String localName, 
             String qName, Attributes attributes) throws SAXException {
       
    }

    @Override
    public void characters(char[] ch, int start, int length) throws SAXException {
        
    }

    @Override
    public void endElement(String uri, String localName, String qName) 
        throws SAXException {

    }

    @Override
    public void endDocument() throws SAXException {
    }
}						|-----------------------------|
						v							  |
startDocument()-->startElement()-->characters()-->endElement()-->characters()-->endDocument() 
xml文件中含有\n 和 \t ，解析完想解析的内容之后，后面紧随的\n 和换行之后缩进带来的\t 同样会执行characters方法。
```

