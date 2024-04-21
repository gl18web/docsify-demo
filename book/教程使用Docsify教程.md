# 0 序言

本教程将粗略讲讲Docsify的使用教程，包括环境搭建及测试。

# 1 准备工作

### 1.1 安装node

首先进入[node官网](https://nodejs.cn/download/)下载Windows安装包（64位）。自行选择安装位置。

> [!NOTE]
>
> 高版本可能出现提示安装necessary tools，不用安装

安装完毕后，可以打开cmd输入以下命令检测是否安装成功

```
node -v     							// 显示node.js版本
npm -v      							// 显示npm版本
```

### 1.2 配置环境

#### 1.2.1 前置

找到安装的目录，在安装目录下新建两个文件夹【node_global】和【node_cache】![配置1.1](..\img\docsify使用\配置1.1.png)

创建完毕后，使用**管理员身份打**开cmd命令窗口，输入

①npm config set prefix “你的路径\node_global” （复制你刚刚创建的“node_global”文件夹路径）

```
npm config set prefix "D:\develop\Node.js\node_global" 示例路径
```

 ②npm config set cache “你的路径\node_cache” （复制你刚刚创建的“node_cache”文件夹路径）

```
npm config set cache "D:\develop\Node.js\node_cache" 示例路径
```

#### 1.2.2 配置

以【此电脑】-单击右键-【属性】-【高级系统设置】-【环境变量】打开面板

![配置1.2](..\img\docsify使用\配置1.2.png)

1.在**【系统变量】**中点击【新建】输入以下：

变量名：NODE_PATH

变量值：C:\Program Files\nodejs\node_global\node_modules

然后你就会发现【node_global】里多出了一个【node_modules】文件夹

> [!Note]
>
> 如果输入变量值之后没有自动创建【node_modules】文件夹，就在【node_global】下手动创建一个【node_modules】文件夹，再复制你创建的【node_modules】文件夹的路径地址到变量值

2.编辑**【用户变量】**中的【Path】

将默认的 C 盘下【 AppData\Roaming\npm】修改成 【node_global】的路径

3.在**【系统变量】**中选择【Path】点击【编辑】**新建%NODE_PATH%**，随后一直点击【确定】

### 1.3 安装模块

在cmd输入以下安装docsify-cli

```
npm i docsify-cli -g
```

建议在科学上网的情况下安装，整个过程大概5min

### 1.4 运行项目及测试

进入到下载好的文件夹**docsify-demo-master**内打开cmd或powershell输入以下命令，即可启动

```
docsify s
```

![QQ截图20240421142022](..\img\docsify使用\QQ截图20240421142022.png)

# 2 文件结构与扩展

## 2.1 基础

其实我们维护一份轻量级的个人&团队文档我们只需要配置以下这几个基本文件就可以了。

| 文件作用                     | 文件          |
| ---------------------------- | ------------- |
| 基础配置项（入口文件）       | index.html    |
| 封面配置文件                 | _coverpage.md |
| 侧边栏配置文件（左边导航栏） | _sidebar.md   |
| 导航栏配置文件（顶部导航栏） | _navbar.md    |
| 主页内容渲染文件             | README.md     |
| 浏览器图标                   | favicon.ico   |

## 2.2 侧边栏配置文件_sidebar.md

如果需要创建多个页面，或者需要多级路由的网站，在 docsify 里也能很容易的实现。例如创建一个 `guide.md` 文件，那么对应的路由就是 `/#/guide`。

假设你的目录结构如下：

```
.
└── docs
    ├── README.md
    ├── xxxx
    └── book
        ├── test1.md
        └── test2.md
```

那么对应的访问页面将是

```
docs/README.md        => http://domain.com
docs/book/README.md  => http://domain.com/book/
docs/book/guide.md   => http://domain.com/book/guide
```

这个时候我们可以对侧边栏进行以下定制，这里以本工程为例

```
- [更新记录](/book/更新日志.md)
- [礼堂舞台的后台操作](/book/调音台.md)
  - [调音台](/book/调音台.md)
- [编程初学必看](/book/编程前置知识.md)
```

则效果为

![侧栏1.1](..\img\docsify使用\侧栏1.1.png)
