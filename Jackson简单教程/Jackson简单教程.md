# 写在最前

JSON的介绍就不过多介绍了，可以直接看w3c对JSON的简短介绍  [W3C-JSON](https://www.w3cschool.cn/json/) 。 这篇文章介绍的Jackson是JSON的一个类库  .
## Jackson
 1. 引入依赖，我这用最新的版本
```
<dependency>
	<groupId>com.fasterxml.jackson.core</groupId>
	<artifactId>jackson-databind</artifactId>
	<version>2.11.0</version>
</dependency>
```
 2. JAVA对象转换JSON  `writeValue`   `writeValueAsString`
```java
public static void main(String[] args) {
   try {
        ObjectMapper mapper = new ObjectMapper();
        Example exa = create();
        /*把java对象内的属性写到example.txt文件*/
        mapper.writeValue(new File("e:\\example.txt"), exa);
    }catch (Exception e) {
        e.printStackTrace();
    }
}

static Example create (){
    Example exa = new Example();
    exa.setValue("values;");
    exa.setColor("red");
    return exa;
}
```
>   example.txt 文件的内容 {"color":"red","value":"values;"}

writeValue不止可以转换成文件，它有很多重载的方法
![重载方法](https://img-blog.csdnimg.cn/20201230094057876.png#pic_left)

```java
try {
    ObjectMapper mapper = new ObjectMapper();
     // 以JSON字符串的形式输出
     String string = mapper.writeValueAsString(create());
     System.out.println(string);
 }catch (Exception e) {
     e.printStackTrace();
 }
```
>  {"color":"red","value":"values;"}

**如果你的JSON字符串较长，那么他的格式将显得非常的乱，你可以指定让他更美化的输出**

```java
try {
    ObjectMapper mapper = new ObjectMapper();
    String beautifulJson = mapper.writerWithDefaultPrettyPrinter().writeValueAsString(create());
    System.out.println(beautifulJson);
}catch (Exception e) {
    e.printStackTrace();
}
```
> {
	  "color" : "red",
	  "value" : "values;"
}

当然你也可以用一些在线的工具来完成这个工作 [JSON格式化](https://www.jsonformatting.com/json-format/)

 3. JSON转换为JAVA对象 `readValue`

```java
ObjectMapper mapper = new ObjectMapper();
Example e = mapper.readValue(new File("e:\\example.txt"), Example.class);
System.out.println(e);
```
> Example(color=red, value=values;)

```java
try {
     ObjectMapper mapper = new ObjectMapper();
     String str = "{\"value\":\"kateliuyi\",\"color\":\"blue\"}";
     Example e = mapper.readValue(str, Example.class);
     System.out.println(e);
 } catch (Exception e){
     e.printStackTrace();
 }
```
> Example(color=blue, value=kateliuyi)

 4. 指定JSON的字段命名 `@JsonProperty`
在本篇文章，Example对象转换为JSON输出的字段名是color、value(是以javabean的属性来决定的), 如果想改变JSON输出的字段命名，需要用到`@JsonProperty`注解

```java
@JsonProperty("changeColor")
private String color;
private String value;
```
> Example(changeColor=blue, value=kateliuyi)
 5.  忽略空的字段  `@JsonInclude`
默认情况下输出的JSON是包含空字符串的 , 如果想忽略空，需要用到`@JsonInclude` 注解
 + `@JsonInclude`应用到类， 表示这个类的所有字段都忽略空
 

```java
try {
    ObjectMapper mapper = new ObjectMapper();
    // 以JSON字符串的形式输出
    String string = mapper.writeValueAsString(create());
    System.out.println(string);
}catch (Exception e) {
    e.printStackTrace();
}

static Example create (){
 	Example exa = new Example();
    /*exa.setValue("values;");(*/
    exa.setColor(null);
    return exa;
 }
```
> {}
+ `@JsonInclude`应用到字段， 只忽略此字段

```java
public class Example {
    @JsonInclude(JsonInclude.Include.NON_NULL)
    private String color;
    private String value;
}

static Example create (){
	Example exa = new Example();
   	exa.setValue(null);
   	exa.setColor(null);
   	return exa;
}
```
> {"value":null}
 6.  忽略指定字段 - `@JsonIgnore`   `@JsonIgnoreProperties`
+ `@JsonIgnore`

```java
public class Example {
    @JsonIgnore
    private String color;
    private String value;
}
```
> {"value":"abc"}
+ `@JsonIgnoreProperties`

```java
@JsonIgnoreProperties({"value"})
public class Example {
    private String color;
    private String value;
}
```
>{"color":"red"}

 7.  对集合的操作
+ `java.util.List`

```java
try {
    ObjectMapper mapper = new ObjectMapper();
    String str = "[{\"color\":\"red\", \"value\":\"kateliuyi\"}, {\"color\":\"blue\", \"value\":\"nas\"}]";
    List<Example> list = Arrays.asList(mapper.readValue(str, Example[].class));
    System.out.println(list);
}catch (Exception e) {
    e.printStackTrace();
}
```
>[Example(color=red, value=kateliuyi), Example(color=blue, value=nas)]
+ `java.util.Map`

```java
try {
    ObjectMapper mapper = new ObjectMapper();
    String string = "{\"name\":\"kateliuyi\", \"value\":\"abc\"}";
    Map<String, String> map = mapper.readValue(string, Map.class);
    System.out.println(map);
}catch (Exception e) {
    e.printStackTrace();
}
```
> {name=kateliuyi, value=abc}


+ 我的网站: [https://www.jsonformatting.com/](https://www.jsonformatting.com/)
+ 我的思否: [https://segmentfault.com/u/json_formatter/articles](https://segmentfault.com/u/json_formatter/articles)