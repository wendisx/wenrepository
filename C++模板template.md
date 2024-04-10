## C++模板template

### content

> 1、[模板的基础介绍](#basic)
>
> 2、[模板的使用](#use)
>
> 3、[模板实例](#example)

### 1、<a name="basic"></a>模板的基础介绍：

模板是泛型编程的基础，在C++中，使用template来声明模板，模板可以简单地理解为泛用代码，这些代码无法被IDE直接编译执行，而是通过生成实例来运行，而生成过程不需要程序员干预，直接由编译器完成。模板也可以理解为重载。

模板简单分为**模板函数**和**模板类**。

#### 模板函数

```C++
template<typename T>//这里T表示泛型，即为任何数据类型
```

#### 模板类

```c++
template<class T>//模板类
```

我们一般认为这两者无本质区别，一般可以套用任何一个。

### 2、<a name="use"></a>模板的使用：

```C++
template<class T>
T swap(T& a,T& b){
    T temp=a;
    a=b;
    b=temp;
}
//模板声明一个swap()函数
template<class T>
    class class_name{
        ...
    }
//模板声明一个模板类
```

### 3、<a name="example"></a>模板实例：

```C++
//最近在学数据结构就简单写个树的节点
#include<iostream>
using namespace std;
template<class T>
struct binarytreenode{
    T element;//数据存储
    binarytreenode* lp,rp;//左右孩子指针
    binarytreenode(){lp=rp=NULL;}
    binarytreenode(T& m){
        element = m;
        lp=rp=NULL;
    }
    binarytreenode(T& m,binarytreenode* leftp,binarytreenode* rightp){
        element=m;
        lp=leftp;
        rp=rightp;
    }
};
```

