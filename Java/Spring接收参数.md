# SpringMVC后台接收参数的几种方式


```java 
@RequestMapping("/test")
    public String  test(@RequestParam(required = false) Map map)  {
        System.out.println("map====>"+map);
        return  "map";
    }
```



```java 
@RequestMapping("/test")
    public String  test(Test test)  {
        System.out.println("test====>"+test);
        return  "test";
    }
```



```java 
@RequestMapping("/test")
    public String  test(@RequestParam("id") String  id,@RequestParam("name") String  name)  {
        System.out.println("id====>"+id);
        System.out.println("name====>"+name);
        return  "test";
    }
```
