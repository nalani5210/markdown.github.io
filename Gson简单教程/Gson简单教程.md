# 写在最前

前面一片文章介绍了Jsckson的使用，这篇介绍一下Gson的使用

## Gson
 1. 引入依赖，我这用最新的版本
```
<dependency>
	<groupId>com.google.code.gson</groupId>
	<artifactId>gson</artifactId>
	<version>2.8.6</version>
</dependency>
```
在引入依赖的时候，出现了问题，一直提示`程序包com.google.gson不存在`， 能正常引入类，就是run的时候不行，很纠结，网上的解决办法都是复制粘贴别人的，解决不了。我分享一下我的解决方法 :
idea左上角 File 菜单， 然后看图点击 ，清理idea的环境并且重启， 重启以后 右键项目 Maven - Reimport 就可以了
![打开idea菜单](https://img-blog.csdnimg.cn/20210104101342182.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_left)

 2. JAVA对象转换JSON  `toJson`

```java
Gson gson = new Gson();
Example example = new Example("blue","abc");
//java对象转换为json字符串
String json = gson.toJson(example);
System.out.println(json);
```
> {"color":"blue","value":"abc"}

 3. JSON字符串转换为JAVA对象 `fromJson`
```java
Gson gson = new Gson();
// json字符串转换java对象
String json = "{'value' : 'csdn' , 'color' : '#000000'}";
Object object = gson.fromJson(json, Example.class);
System.out.println(object);
```
> Example(color=#000000, value=csdn)

**如果你的JSON字符串较长，那么他的格式将显得非常的乱，你可以指定让他更美化的输出**

```java
Gson gson = new GsonBuilder().setPrettyPrinting().create();
Example example = new Example("blue","abc");
String json = gson.toJson(example);
System.out.println(json);
```
> {
  "color": "blue",
  "value": "abc"
}

当然你也可以用一些在线的工具来完成这个工作 [JSON格式化](https://www.jsonformatting.com/json-format/)

 4. 忽略字段  
 
 	a. `excludeFieldsWithModifiers`
	###### 默认情况下，transient和static字段将被排除.
 + 只忽略static
 
```java
new GsonBuilder()
            .excludeFieldsWithModifiers(Modifier.STATIC)
            .create();
```
 + 忽略static和transient
```java
new GsonBuilder()
            .excludeFieldsWithModifiers(Modifier.STATIC, Modifier.TRANSIENT)
            .create();
```
+ 默认方法`excludeFieldsWithModifiers`忽略static和transient
+ 
   [transient简单学习](https://www.cnblogs.com/lanxuezaipiao/p/3369962.html)

 	b. `@Expose`
	###### @Expose可以自定义哪些字段被排除
```java
new GsonBuilder()
            .excludeFieldsWithoutExposeAnnotation()
            .create();
```
```java
@Expose(serialize = true, deserialize = true)
    private String color;
    private String value;
```
> {"color":"blue"}
 5. 显示null
	###### 默认情况下，null对象是被忽略掉的
	

```java
Gson gson = new GsonBuilder().serializeNulls().create();
Example example = new Example("blue",null);
String json = gson.toJson(example);
System.out.println(json);
```
> {"color":"blue","value":null}
 6.  对集合的操作
+ `java.util.List`

```java
Gson gson = new Gson();
String jsonList = "[{\"color\":\"red\",\"value\":\"abc\"}, {\"color\":\"blue\",\"value\":\"kk\"}]";
List<Example> data = gson.fromJson(jsonList, new TypeToken<List<Example>>() {}.getType());
data.forEach( item -> {
    System.out.println(item);
});
```
> Example(color=red, value=abc)
Example(color=blue, value=kk)

+ `java.util.Map`

```java
Gson gson = new Gson();
String jsonMap = "{\"color\":\"red\",\"value\":\"abc\"}";
Map<String, Object> map = gson.fromJson(jsonMap, new TypeToken<Map<String, Object>>() {}.getType());
map.forEach((x, y) -> System.out.println( x + " " + y));
```
> color red
value abc


+ 我的网站: [https://www.jsonformatting.com/](https://www.jsonformatting.com/)
+ 我的思否: [https://segmentfault.com/u/json_formatter/articles](https://segmentfault.com/u/json_formatter/articles)