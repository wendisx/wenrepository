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
> [序列化和反序列化](#serialization)

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

## <a name="fileinputstream">字节流FileInputStream</a>

```java
import java.io.*;
public class fileinputstreamdemo{
    public static void main(String[] args){
        try{
            FileInputStream f= new FileInputStream("文件路径");
            String[] data= new String[读取长度];
            int count=0;
            while((count=f.read(data))!=-1){
               System.out.println(data);
            }
            if(f!=null){
                try{
                    f.close();
                    System.out.println("字节流关闭成功");
                }catch(IOException e){
                    e.printStackTrace();
                }
            }
        }catch(IOException e){
            e.printStackTrace();
        }
    }
}
```

## <a name="fileoutputstream">字节流FileOutputStream</a>

```java
import java.io.*;
public class fileoutputstreamdemo{
    public static void main(String[] args){
        try{
            FileOutputStream f= new FileOutputStream("文件路径",true/false);//true为在文件末尾写入，false表示清空文件从头开始写
            String data={写入数据/内容};
            Byte[] bdata=data.getBytes();//转化成字节
           f.write(bdata);
            f.flush();//写完后刷新流确保数据不被丢失
        }catch(FileNotFoundExcception e){
            e.printStackTrace();
        }catch(IOException e){
            e.printStackTrace();
        }finally{
            if(f!=null){
                try{
                    f.close();
                    System.out.println("文件流关闭成功");
                }catch(IOException e){
                    e.printStackTrace();
                }
            }
        }
    }
}
```

## <a name="serialization">序列化和反序列化</a>

```java
/*java序列化和反序列化是通过java.io.Serializable实现的,因此，要实现序列化，需要先对类实现接口*/
public interface Serializable{
    /*序列化接口;*/
}
//以下以学生类为例
public class Student implements Serializable{
    private int id;
    private String name;
    public Student(int id,String name){
        this.id=id;
        this.name=name;
    }
    ...all of your methods
}
//实现序列化
import java.io.*;
public class SerializableDemo{
    public static void main(String[] args) throws Exception{
        Student stu1 = new Student(100000,"张三");
        FileOutputStream f= new FileOutputStream("FILE_PATH");
        ObjectOutputStream fout=new ObjectOutputStream(f);
        fout.writeObject(stu1);
        fout.close();
        f.close();
    }
}
//实现反序列化
import java.io.*;
public class DeSerializationDemo{
    Student stu2=null;
    public static void main(String[] args) throws Exception{
        ObjectInputStream fin=new ObjectInputStream(new FileInputStream("FILE_PATH"));
        stu2=(Student)fin.readObject();
       fin.close();
    }
}
```

