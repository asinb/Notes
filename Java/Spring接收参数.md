# SpringMVC后台接收参数的几种方式

## 获取参数用map，前端不要随便变  否则容易错

```java 
@RequestMapping("/test")
    public String  test(@RequestParam(required = false) Map map)  {
        System.out.println("map====>"+map);
        return  "map";
    }
```



## 默认前端传的字段和后端一直就能匹配上。

```java 
@RequestMapping("/test")
    public String  test(Test test)  {
        System.out.println("test====>"+test);
        return  "test";
    }
```

## 指定接收参数。

```java 
@RequestMapping("/test")
    public String  test(@RequestParam("id") String  id,@RequestParam("name") String  name)  {
        System.out.println("id====>"+id);
        System.out.println("name====>"+name);
        return  "test";
    }
```



