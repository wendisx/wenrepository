## 一个简单的java IO流小作业

今天（2024年4月15日），在工作室培训，学习的是java io流，最后有一个小作业是有关复制文件的操作，要求通过Java io流实现，我写了很久，最后是在学姐的提示下才完成的。（感谢学姐提醒），然后打算写本文章来记录一下学习过程与自己对Java io的一些看法。

## content

> [文件操作 ](#filework)
>
> [字符流FileReader](#filereader)
>
> [字符流FileWriter](#filewriter)
>
> [简单实例](#example)
>
> [字节流FileInputStream](#fileinputstream)
>
> [字节流FileOutputStream](#fileoutputstream)
>
> [序列化和反序列化](#serialization and deserialization)

## <a name="filework">文件操作</a>

```java
import java.io.*;  //引入io包，便于后续饮用
public class filework{
    public static void main(String[] args){
        File f = new File("src\\文件名");//创建文件对象
        //创建文件
        if(f.exists()){
            System.out.println("文件已经存在");
        }else{
           try{
               f.creatNewFile();
               System.out.println("文件创建成功");
           }catch(Exception e){
               e.printStackTrace();//打印文件创建异常&其他异常处理操作
           }
        }
    }
}
```

## <a name="filereader">字符流FileReader</a>

```java
import java.io.*;
public class filereaderdemo{
    public static void main(String[] args){
        try{
            BufferedReader r = new BufferedReader(new FileReader("src\\文件名"));
            String data=null;
            while((data=r.readLine())!=null){
                System.out.println(data);//打印内容
            }
            r.close();//关闭r
        }catch(IOException e){
            e.printStackTrace();
        }
    }
}
```

## <a name="filewriter">字符流FileWriter</a>

```java
import java.io.*;
public class FileWriterdemo{
    public static void main(String[] args){
        try{
            BufferedWriter w =new BufferedWriter(new FileWriter("src\\文件名"));
            while(写入条件){
               w.write();//写入内容
        }
            w.close();
    }catch(IOException e){
            e.printStackTrace();
        }
}
```

## <a name="example">简单实例</a>

```java
/*本实例实现了指定的文本文档实现复制到另一个指定文档*/
import java.io.*;
import java.util.Scanner;
public class copydemo{
    public static void main(String[] args){
        String oldtext,newtext;
        Scanner in = new Scanner(System.in);
        System.out.println("注意:你的文本路径必须是有效的绝对路径！！！");
        System.out.println("请输入旧文本文档路径：");
            oldtext =in.nextLine();
        System.out.println("请输入新文本文档路径：");
        	newtext = in.nextLine();
        try{
            BufferedReader r = new BufferedReaer(new FileReader(oldtext));
            BufferedWriter w = new BufferedWriter(new FileWriter(newtext));
            String data=null;
            while((data=r.readLine())!=null){
                w.writer(data);//数据复制
                w.newLine();//换行
            }
            //关闭流
            w.close();
            r.close();
        }catch(IOException e){
            e.printStackTrace();
        }
    }
}
```

