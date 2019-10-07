
* @Qualifier:意思是合格者，通过这个标示，表明了哪个实现类才是我们所需要的，添加@Qualifier注解，需要注意的是@Qualifier的参数名称为我们之前定义Bean的名称之一
```
    @Bean("routingDataSource")
    public DataSource myRoutingDataSource(@Qualifier("masterDB") DataSource masterDataSource,
                                          @Qualifier("slaveDB") DataSource slaveDataSource
    ) {
```
* @Configuration标注在类上，相当于把该类作为spring的xml配置文件中的<beans>，作用为：配置spring容器(应用上下文)
* @PropertySource：可以指定自定义的properties文件，为Spring 中的 Environment提供方便和声明机制，通常与Configuration   一起搭配使用，将properties文件的属性加入到Environment中，也可以指定读取文件的编码方式，避免乱码
```
  @Configuration
  @PropertySource(value = "classpath:application.properties",encoding="utf-8")
```
* @ConfigureProperties:可以根据后缀来指定业务需要类型的配置 属性，但是该类的属性必须生成getter和setter的函数，否者映射不成功
```
  @Configuration
  @PropertySource(value = "classpath:application.properties",encoding="utf-8")
  @ConfigurationProperties(prefix="com.huawei")
  public class ConnectionSettings {
    private String username;
    private String remoteAddress;
    private String password ;
    public String getUsername() {
        return username;
    }
    ....  
```
* @Value:根据配置文件的属性直接注入
```
  @Configuration
  @PropertySource("classpath:db.properties")
  public class DBConnection {
    @Value("${DB_DRIVER_CLASS}")
    private String driverClass;
```
