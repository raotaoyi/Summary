
* @Qualifier:意思是合格者，通过这个标示，表明了哪个实现类才是我们所需要的，添加@Qualifier注解，需要注意的是@Qualifier的参数名称为我们之前定义Bean的名称之一
```
    @Bean("routingDataSource")
    public DataSource myRoutingDataSource(@Qualifier("masterDB") DataSource masterDataSource,
                                          @Qualifier("slaveDB") DataSource slaveDataSource
    ) {
```
