

# 这是一个信息帮助网站

欢迎来到十八中帮助页面,看不见评论区请科学上网，欢迎留言纠错或者提issue

## 书写规范

1.建议使用Typora进行文档编辑

2.主目录请写在**README.md**文件下。如果不会写文件引用，请直接写在本文件下。

3.文章**大标题**使用**二级标题**，**小标题**使用**三级标题**，**正文**不使用**段落**。

4.在编程帮助页代码请严格使用**代码块**，需要说明其他的请使用**警告框**

5.图片放在**/img**文件夹下

> **[!重要]**
>
> **编辑前先git一下库，并在提交GitHub前在群里说明，以免顶掉文件。**



------

## Typora的运用

### 激活方法

打开安装目录找到\Typora\resources\page-dist\static\js\LicenseIndex.180dd4c7.5c394f9a.chunk.js文件

用记事本打开，搜索关键代码e.hasActivated=“true”

![typora激活](img\typora激活.png)

将搜索到的位置的【e.hasActivated="true"==】 后面添加 【"true",】
即：e.hasActivated="true"=="true",

### 基本操作

在**文件（F）**栏中，可以找到**打开文件夹**选项选择工程文件夹，即可在右栏打开待编辑的rd文件。

在**段落（P）**栏中，可以找到对应的标题级别，和对文段进行具体的操作。建议自己去试，一个个描述起来过于抽象。

在**格式（O）**栏中，可以对文本进行具体操作。

> [!IMPORTANT]
>
> 特别的！在插入图片时，请修改图片路径为**/img/xxxxxx.jpg**。
>
> 例如“(img\typora激活.png)”这些格式

多用 多试 就会了

## 关于代码的提交（GIT）

在Github网页端的提交不再做赘述，自己百度或者乱点点。英文都看得懂，不会的可以滚了。

下面介绍Git的用法

### 下载及安装

1.点击[git下载页](https://git-scm.com/download/win)中的**[64-bit Git for Windows Setup](https://github.com/git-for-windows/git/releases/download/v2.44.0.windows.1/Git-2.44.0-64-bit.exe)**进行下载

2.打开安装程序，自己选择安装路径，其他的一直跳过（点确定）

### 绑定账号及初始化

#### 一些基本设置

1.打开git bash进行设置

```git bash
git config --global user.name '你的用户名'
git config --global user.email '你的邮箱'
```

2.在你要创建工程的目标文件夹内运行以下命令，来初始化git仓库

```git bash
git init
```

执行该命令之后，就可以在当前目录下生成.init文件夹，并且会默认生成一个master分支。

3.使用git clone命令可以从Git仓库拷贝项目，类似于SVN中的 svn checkout，命令格式为：

```
git clone <url> [directory]
```

url为git仓库地址，directory为本地目录，比如，要克隆某个Git 代码仓库，可以用下面的命令：

```
git clone git://github.com/xxxxx/xxxx.git
```

执行完成之后会在当前目录下生成仓库，如果要指定目录下生成，则可以在后面加一个具体的位置路径，如：

```
git clone git://github.com/xxxxx/xxxx.git newgit
```

 git clone 时，可以用不同的协议，包括 ssh, git, https 等，其中最常用的是 ssh，因为速度较快，还可以配置公钥免输入密码，各种写法格式如下：

```
git clone git@github.com/schacon/grit.git         --SSH协议
git clone git://github.com/schacon/grit.git       --GIT协议
git clone https://github.com/schacon/grit.git     --HTTPS协议
```

#### 推送的操作（push时要科学上网）

##### Git 远程仓库

 前面我们使用到的 Git 命令都是在本地执行，如果你想通过 Git 分享你的代码或者与其他开发人员合作。 你就需要将数据放到一台其他开发人员能够连接的服务器上。本本将使用 Github 作为远程仓库，来介绍Git 远程仓库的使用。
下面介绍远程仓库常用的几种指令：

- **git remote add**：添加远程仓库
- **git remote**：查看当前的远程仓库
- **git fetch**、**git pull**：提取远程仓仓库
- **git push**：推送到远程仓库
- **git remote rm**：删除远程仓库

##### 1.**git remote add**

git remote add可以添加一个远程仓库，其命令格式如下：

```
git remote add [alias] [url]
```

参数[alias]为别名， [url]为远程仓库的地址，如：我们可以将  https://github.com/gl18web/docsify-demo.git   仓库添加到本地，并命名为test

```
git remote add test https://github.com/gl18web/docsify-demo.git
```

##### 2.git push

git push 推送你的新分支与数据到某个远端仓库命令，格式如下：

```
git push [alias] [branch]
```

如：我们可以将前面提交的文件push到远程仓库中：

```
git push test master
```

#### ssh密钥的设置

这个自己上网搜，懒得讲。不会就直接在网页端上传

#### 关于使用VSC来提交库

当你成功安装git和插件时（我没装也能用），VSC会在左栏显示一个**源代码管理器**图标。如果你有更改项，它会高亮并显示相关文件，例如我修改了README.md文件，如图：

![git上传](img\git上传.png)

提交的时候请在消息栏著名日期或者其他事项，方便大家辨认。

可以点开具体文件查看是否有效更改：![辨认更改](img\辨认更改.png)

点击提交在输出栏可以看到Git相关日志。如果长时间未显示上传字样就说明网络连接超时。

![同步更改](img\同步更改.png)
