## SSM技术

> 前期准备(applicationContext.xml和pom.xml配置)
>
> Spring
>
> SprinMVC
>
> Maven-Plus
>
> Mybatis-Plus

### 前期准备(applicationContext.xml和pom.xml配置)

```xml
<!--pom.xml配置-->
<!--导入spring-context依赖-->
<dependency>
    //导入依赖
</dependency>
//导入后刷新maven配置
```

```xml
<!--applicationContext.xml配置-->
<beans>
    <bean id="类的唯一标识" name="类的别名" class="类">
  			<property name="标识名" ref="建立关系类的标识"/>      
    </beans>
</beans>
```



### Spring

>IoC容器
>
>DI
>
>Bean
>
>setter注入
>
>构造器注入
>
>自动装配
>
>纯注解开发(常用)
>
>Spring整合mybatis
>
>Spring整合

#### IoC容器

管理类的容器，每一个类的管理称为bean

#### DI

建立类之间的关系

#### Bean

是类在ioc中的表现形式

```java
/*xml中的<bean></bean>本质上是创建了对象，而且只能调用默认无参的构造方法
，否则抛出异常*/
public class BookDaoImpl implements BookDao{
    public BookDaoImpl(){
        //被调用
    }
    public others methods(){
        //伪代码表示其它方法
    }
}
```

#### setter注入

```java
public class class_name{
    //字段（包含基本数据类型，可以是类的对象）
    public void set[字段名](type element){
        this.字段=element;
    }
}
/**
对应xml配置文件
*/
<property name="类中字段名" ref="类">
<property name="类中字段名" value="值">
```

#### 构造器注入

```java
/**
原理同上将setter方法换成带参数构造函数即可
xml配置中将peoperty换成constructor即可
*/
```

#### 自动装配

```java
/**
<bean id="" class="" auto...="自动装配的方法" >
*/
```

#### 纯注解开发

```java
//定义bean
数据层：@Repository
控制层：@Controller
服务层：@Service
一般使用：@Component
//纯注解开发
    @Configuration
    @ComponentScan({})
    AnnotationConfigApplicationContext
//bean的作用范围和生命周期
    @Scope("singleton/prototype")
    @PostContructor
    @PreDestroy
//自动装配
    @Autowired
    @Qualifier("bean_id")
    @Value("${}")+@PropertySource({....})
//第三方管理bean
    在pom.xml中导入jar包
    @Bean+method(return)
    @Import({Config_class})//在SpringConfig中
```

![](E:/素材bag/图片/概念/spring注解开发.jpg)

#### Spring整合mybatis

