# SpringMVC的实现

1.继承Servlet的HttpServlet实现事件分发；

2.创建自己的注解类

> - 实现了@Controller注解
> - 实现@RequestMapping注解 

3、相关知识点

1）根据包名获取当前路径

```
//以下两种方式类路径下的根目录：
//运行结果都是  file:/D:/work_space/java/bin/
    class.getResource("/");
    或者
    class.getClassLoader.getResource("");
    
    URL url = this.getClass().getResource("/");
    File baseFile = new File(url.getFile());

```

2）读取配置文件

配置文件一般放在resources文件夹下，被编译后直接放在class目录下，因此可以直接使用对应的名称获取文件。
同样使用Properties加载配置文件，这样就可以该类进行很方便的读取资源文件的内容。

```
    class.getResource("/application.properties");
    或者
    class.getClassLoader.getResource("application.properties");
    
    System.out.println(this.getClass().getResourceAsStream("/"+"application.properties"));
    System.out.println(this.getClass().getClassLoader().getResourceAsStream("application.properties"));
        
    //文件读取方式    
    Properties properties = new Properties();
    properties.load(this.getClass().getResourceAsStream("/"+"application.properties"));

```
