### git配置&基础操作

#### 连接远程仓库

选用示例：github(gitee)

[github](https://github.com/)

[gitee](https://www.bing.com/ck/a?!&&p=c6aab1b23a328760JmltdHM9MTcxMjE4ODgwMCZpZ3VpZD0zMGE3MzgyNi1mMmY2LTZhNzktM2M4Zi0yYjFmZjMyNDZiMmQmaW5zaWQ9NTIwNg&ptn=3&ver=2&hsh=3&fclid=30a73826-f2f6-6a79-3c8f-2b1ff3246b2d&psq=gitee&u=a1aHR0cHM6Ly9naXRlZS5jb20v&ntb=1)

##### 第一步：

> github上注册账号(邮箱+密码)
>
> github上新建一个仓库(仓库主分支默认为main分支，如果习惯master作为主分支可以自行更改)
>
> 电脑上准备好git，同时配置好git环境，详细见[git安装与配置]([Git的安装和环境变量的配置_git环境变量-CSDN博客](https://blog.csdn.net/weixin_45811256/article/details/130925392))

##### 第二步：

> 首先，为了后续工作方便，配置SSH密钥，详细见[githubSSH密钥配置]([Github配置ssh key的步骤（大白话+包含原理解释）_github生成ssh key-CSDN博客](https://blog.csdn.net/weixin_42310154/article/details/118340458))
>
> 密钥配置好后，我们就可以开始我们的写代码之旅了

##### 第三步：

```
配置流程：
1、新建工作目录(文件夹)，在工作目录中右键更多选项点击open git bash here选项进入终端
2、git init [content] --第一个命令，创建仓库，将目前目录作为新仓库，当前目录下将生成一个.git文件夹来存放git的必要文件
3、git remote add origin[shortname] [url]  --添加我们的github上的远程仓库，并且为其取一个别名叫做origin，[url]是仓库的http地址
4、git remote  --查看当前连接的远程库
git remote rm [仓库别名]  --删除一个远程仓库
5、git clone [url]  --将远程仓库项目克隆至本地运行,注意clone只能跟仓库的http地址而不能是别名
6、此时，相信你的工作目录下会出现你的仓库的副本，你可以开始对里面的文件修改和提交，此时，基本配置完成
7、git config --list  --查看git基本配置信息\
8、git config --global user.name "用户名字"
9、git config --global user.email 用户邮箱
```

##### 第四步：

```
基本操作：
1、git add [document]/.  --提交更改到暂存区
2、git status  --查看暂存区状态
3、git commit -m '提交信息'/"提交信息"  --git bash可以用单双引号而win下只能使用双引号
4、git push origin[仓库别名] [brunch]  --推送到github上的对应分支中
5、git pull [remote_brunch]:[local_brunch]  --拉取远程仓库分支与本地分支合并
```

##### 第五步：

> [分支操作详情](https://www.runoob.com/git/git-branch.html)
>
> [其他基本操作](https://www.runoob.com/git/git-basic-operations.html)
>
> [查看提交历史](https://www.runoob.com/git/git-commit-history.html)

###### 最后：

[全部详解](https://www.runoob.com/git/git-tutorial.html)