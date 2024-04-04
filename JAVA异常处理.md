### JAVA异常处理

#### 理解异常

> 检查型异常：通常由用户错误操作造成，一般无法预见的异常。
>
> 运行时异常：可以避免的异常，在编译时可以忽略。
>
> 错误：非异常，脱离控制，通常被忽略。

#### Exception类层次

![](E:\素材bag\图片\概念\Java异常处理关系.png)

#### JAVA内置异常&方法

[详细介绍](https://www.runoob.com/java/java-exceptions.html)

#### 捕获异常&throw相关操作

```java
/*try...catch...finally捕获异常*/
try{
    //需要执行的代码
}
catch(Exceptionname e){
    //捕获对应异常后执行的代码
}

/*多重捕获*/
try{
    
}
catch(exceptionname1 e1){
    
}
catch(exceptionname2 e2){
    
}
...
finally{
    //一定执行的代码
}
```

```java
/*throw/throws关键字*/
throw new exceptionname();//抛出一个异常
public back_type method() throws 异常1，异常2，...{
    
}//throws表示声明方法可能抛出的异常，如果方法抛出了匹配类型的异常，由调用该方法的代码处理异常
```

#### try-with-resources

```java
try(open resources){
    //use resources
}catch(exception e){
    //处理异常同时关闭资源
}
/*try()中的可以打开多个资源通过;连接
```

#### 声明自定义异常类

> 所有异常类必须是Throwable类的子类
>
> 写一个检查型的类要继承Exception类
>
> 写一个运行时的类要继承RuntimeException类

```java
class myexception extends Exception{
    //检查型异常
};
class myexception extends RuntimeException{
    //运行时异常
};
```

