### Maven配置与IDEA配置

#### Maven安装与配置

> 下载安装Maven，[Maven官网](https://maven.apache.org/)
>
> 在电脑系统环境变量里添加Maven_HOME(其他取名也行，总之配置好Maven就行)
>
> 电脑打开cmd终端，输入mvn -v查询是否配置成功

maven会从中央仓库下载jar包到本地仓库中，这个仓库时maven创建的默认仓库，这个地址路径可以修改

> 打开settings.xml文件
>
> 在maven的默认仓库下建立自己的仓库，使用如下语句添加，将原本默认地址注释
>
> `<localRepository>本地仓库实际地址</localRepository>`
>
> 向下找到<mirrors>...</mirrors>并且注释，在mirrors区域写入如下语句
>
> `<mirrors>
>     <mirror>
>     	<id>alimaven</id>
>     	<name>aliyun maven</name>
>     	<url>http://maven.aliyun.com/nexus/content/groups/public/</url>
>     	<mirrorOf>*</mirrorOf>
>     </mirror>
>   </mirrors>`
>
> 此处我们将仓库定位在阿里云，想必每次到中央仓库下载jar包块很多
>
> 再向下找到<profiles></profiles>注释掉，并修改为自己项目打包的jdk版本，以下代码演示
>
> `	<profile> 
>       <id>jdk-1.8</id>  
>       <activation>
> 		<activeByDefault>true</activeByDefault>
>         <jdk>1.8</jdk>  
>       </activation><properties>  
>         <maven.compiler.source>1.8</maven.compiler.source>  
>         <maven.compiler.target>1.8</maven.compiler.target>        <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>  
>       </properties>   
>     </profile>`
> 至此，maven配置完成

#### IDEA配置