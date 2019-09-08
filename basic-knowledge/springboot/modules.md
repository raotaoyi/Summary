1.SpringBoot应用将自动使用logback作为应用日志框架，

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-logging</artifactId>
</dependency>
2.得到一个直接可执行的web应用，当前项目下直接运行mvn spring-boot:run 就可以直接启动一个嵌入tomcat服务请求的web应用。

默认访问地址：http://localhost:8080

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
如果想使用其它容器，可引入spring-boot-starter-jetty

另外可以修改server.port使用自己指定的端口

3.访问数据库依赖此模块。

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-jdbc</artifactId>
</dependency>
4.负责web应用安全，配合spring-boot-starter-web使用

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
</dependency>
5.监控，了解应用的运行状态

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>