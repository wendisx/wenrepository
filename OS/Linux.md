### Linux指令

前置知识：

>Linux根目录
>
>Linux路径
>
>>绝对路径
>
>>相对路径
>
>>特殊路径表示
>
>Linux权限
>
>>普通用户
>
>>super user(管理员)
>
>>sudo
>>
>>三种权限
>>
>>>r---只读
>>>
>>>w-只写
>>>
>>>x-可执行
>
>Linux通配符
>
>管道符
>
>重定向符

```shell
根目录:/
绝对路径:/.../.../......
相对路径:......
特殊路径表示:
./
..
~
管理用户权限进入&退出:su - root/exit,ctrl+c
通配符
*name尾匹配
name*头匹配
*name*包含匹配
管道符
| ------ 表示前指令结果是后指令的参数
重定向符
> ------ 表示将左边的结果覆盖写入到右边
>> ------ 表示将左边的结果追加写入到右边
`指令`：在echo中按照指令处理，避免echo直接输出
sudo:普通指令（具有管理权限，需要配置）
配置方式：
su - root 
visudo
gg
普通用户 ALL=(ALL)		NOPASSWD：ALL
:wq
exit
三种权限
ls -l
[d/-/l][rwx-][rwx-][rwx-]
[文件所属类型][用户权限][用户组权限][其它用户权限]
数字表示(二进制)
r--100
w--10
r--1
组合按照二进制加法
```

指令学习:

>ls
>
>pwd,cd
>
>mkdir
>
>cp,mv,rm
>
>touch,cat,more
>
>which,find
>
>grep,wc
>
>echo,tail
>
>用户和用户组指令
>
>chmod,chown
>
>下载软件
>
>服务操作

```shell
显示当前目录内容
ls [-a -l -h] [文件夹路径]
显示当前工作目录
pwd
切换目录
cd [文件夹路径]
创建文件夹
mkdir [-p] [文件夹路径]
复制,移动,删除
cp 路径1 路径2
mv 路径1 路径2
rm [-r -f] 文件1 文件2 文件3 文件4 文件5 ...
创建文件,打开文件,批量读取文件
touch ...
cat ...
more ...
指令搜索,文件查找
which 指令
find 起始路径 -name "文件名"
find 起始路径 -size +/-[K/M/G]
筛选内容，展示文本属性(使用管道符)
grep [-n] "筛选关键词" 路径
wc [-c -w -m -l] 路径
打印内容，动态追踪(使用重定向符)
echo "内容"
tail [-f -number] 路径
用户和用户组指令
groupadd 组名
grouddel 组名
useradd [-g -d] 用户名
userdel [-r] 用户名
id 用户名
getent PASSWD
getnet group
更改文件权限，更改文件用户和用户组
chmod [-R] [xxx(-num)][u=xxx,g=xxx,o=xxx] 路径
chown [-R] 用户:用户名 路径
下载软件
sudo yum [-y] install/remove/search 软件包
服务操作
systemctl start/stop status enable/disable 服务
```

