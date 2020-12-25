##JSON

+ JSON的优势
+ JSON的劣势
+ JSON在JAVA的简单使用

###JSON的优势
JSON(JavaScript Object Notation) 是一种**轻量级**的数据交换格式，它的**可读性**、**可扩展性**、**简易程度**都比XML要好很多，所以现在已经成为主流的数据传输格式 。

###JSON的劣势
  1. 没有日期类型
  2. 内联没法注释
  3. JSON字段过长时，其格式就会显得非常凌乱


###JSON在JAVA的简单使用

  1. 在pom.xml添加JSON的依赖 (可以在<a href="https://mvnrepository.com/artifact/org.json/json"  target="_blank">maven json</a>找到最新的版本)

   	<dependency>
		<groupId>org.json</groupId>
	    	<artifactId>json</artifactId>
	    	<version>20200518</version>
	</dependency>

  2. 有了依赖，我们先看JSON里面最基本的用法

  3.  JSONObject
 
   >类似于JAVA里面的MAP对象，键值对的存储，没有顺序；
   >key值唯一，value可以放对象(object)
   >多个构造函数
   >更多见官方介绍  <a href="https://stleary.github.io/JSON-java/org/json/JSONObject.html"  target="_blank">JSONObject</a>

  4.  创建JSON

    JSONObject json = new JSONObject();
    json.put("name" , "小明");
    json.put("age" , 16);
    json.put("sex" , true);

 > 预期的返回结果应该是  {"sex":true,"name":"小明","age":16} ， 这就是一个最简单的JSON

  5.  将map对象转换为JSON

    Map<String, String> maps = new HashMap<>(16);
    maps.put("type" , "0");
    maps.put("dispa" , "nkl");
    maps.put("name" , "wu");

    JSONObject obj = new JSONObject(maps);
     
 > 预期的返回结果应该是 {"name":"wu","type":"0","dispa":"nkl"} ， 这是一个由map转换而来的JSON     

  6.  JSONArray
 
   >值可以是任何类型的任何值
>构造函数可以将JSON文本转换为Java对象，toString可以转换为JSON。
>字符串可以用' （单引号）引起来
>更多见官方介绍  <a href="https://stleary.github.io/JSON-java/org/json/JSONArray.html"  target="_blank">JSONArray</a>


  7.  创建JSONArray

    /*创建一个JSONArray对象*/
    JSONArray array = new JSONArray();
    array.put("i am array");
    array.put(true);

    /*输出JSONArray*/
    logger.info(array.toString());

    /*创建一个JSONObject对象*/
    JSONObject json = new JSONObject();
    json.put("name" , "小明");
    json.put("age" , 16);
    json.put("sex" , true);

    /*将JSONObject加到JSONArray对象内*/
    array.put(json);
    /*再次输出JSONArray*/
    logger.info(array.toString());

 > 第一次的预期结果 ["i am array",true]
 > 第二次的预期结果 ["i am array",true,{"sex":true,"name":"小明","age":16}]

+ 如果你的JSON过长导致格式不清晰，你可以用<a href="https://wwww.jsonformatting.com/jsonformat/"  target="_blank">JSON格式化</a>来格式化JSON


 8.  List转换JSONArray

    List<String> data= new ArrayList<>(16);
    data.add("bolg");
    data.add("hello");
    data.add("wuha");

    JSONArray array= new JSONArray(data);
    logger.info(array.toString());

 > 预期结果 ["California","Texas","Hawaii","Alaska"]