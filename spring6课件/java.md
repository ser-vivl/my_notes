maven
vscode

spring

创建项目
- 前置插件 **Extension Pack for Java** 和 **Spring Boot Extension Pack**
- Ctrl+Shift+P然后**`Spring Initializr`**，选择 `Spring Initializr: Generate a Maven Project`**（或 Gradle）
- 向导会依次询问语言、Group Id、Artifact Id、打包方式、Java 版本、Spring Boot 版本以及需要哪些依赖（如 Spring Web、Thymeleaf 等）
- 添加依赖包，然后Ctrl+Shift+P再Maven: Reload Project

spring6解答
为什么第一个案例中要使用bean去创建对象？
答：将创建对象的控制权交给了 Spring 容器（也就是IOC思想）：
- `bean.xml` 里描述“`user` 这个对象是什么类、依赖什么、怎么初始化”
- 容器负责读配置、创建对象、注入依赖、管理生命周期
- 调用方只需要按名字要一个对象，不关心它怎么来的
比如说创建对象需要层层嵌套的时候，每次new一个User都很麻烦
UserDao dao = new UserDao(new DataSource(...));
User user = new User(dao);
但是现在好像也不这么写了

使用log4j2

IOC
基于XML

基于注入

shift alt a 长注释


1.使用rest client插件，直接新建一个.http文件，在里面写入内容后发送，发送一个包验证后端连通性

2.lombok
配置lombok，vscode插件Lombok Annotations Support for VS Code
maven中添加依赖包
<dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <version>1.18.10</version>
</dependency>

3.读取配置信息
为什么代码中没写读取文件的代码，也能读取配置文件信息？
因为**Spring Boot 启动时，会自动去读 `application.yml` 或 `application.properties`**

4.简单的springboot helloword

5.异常处理，**所以异常处理的作用是：把"程序内部的错误"，变成"用户能看懂的信息"。**
1. 使用 `@ControllerAdvice` 和 `@ExceptionHandler` 处理全局异常
2. `@ExceptionHandler` 处理 Controller 级别的异常
3. `ResponseStatusException`
我们只需要在类上加上`@ControllerAdvice`注解这个类就成为了全局异常处理类，当然你也可以通过 `assignableTypes` 指定特定的 `Controller` 类，让异常处理类只处理特定类抛出的异常。

6.**JPA 是 Java 官方定的"操作数据库的规范"，全称是 Java Persistence API。**
它的核心思想是：**让您用"操作 Java 对象"的方式，去操作数据库里的数据，不用手写 SQL。**