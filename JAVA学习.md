## JAVA学习记录

> [异常处理](#exception)
>
> [java注解](#complain)
>
> [java IO流](#iostream)

## <a name="exception">异常处理</a>

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

## <a name="complain">java注解</a>

[详细使用方法](https://www.runoob.com/java/java-documentation.html)<-------请点击这里，进入痛苦之海。

## <a name="iostream">javaIO流</a>

> [认识IO流](#ios)
>
> [IO流的分类](#destinguish)
>
> [需要掌握的IO流](#need)

### <a name="ios">认识IO流</a>

​		IO流，即输入输出，用于完成硬盘文件的读和写的操作。

Istream:输入流

Ostream:输出流

### <a name="distinguish">IO流的分类</a>

1、按照**流的方向**：

**输出流**和**输入流**

2、按照**读取数据**的方式：

**字符流**和**字节流**

字符流：仅能读取普通文本文件或者纯文本文件(能用txt打开的文件，无法打开word文档)

字节流：万能流，可以打开任何形式的文件

```java
字节流：
    java.io.InputStream;//输入流
    java.io.OutputStream;//输出流
字符流：
    java.io.Reader;//输入流
	java.io.Writer;//输出流
/*注意*/
所有流都实现了java.io.Closeable接口;
使用完流一定要用close()关闭流
所有输出流都实现了java.io.Flushable接口；
使用完流要调用flush()刷新流通道以防数据丢失
```

### <a name="need">需要掌握的IO流</a>

[详细使用请点击这里](https://blog.csdn.net/qq_44715943/article/details/116501936#t3)