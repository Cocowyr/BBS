# BBS

### Swift编写的iOS端和服务器端, 服务器端基于Perfect框架

![](https://github.com/SimleCp/BBS/blob/master/ScreenShot/1.png)

![](https://github.com/SimleCp/BBS/blob/master/ScreenShot/2.png)

![](https://github.com/SimleCp/BBS/blob/master/ScreenShot/3.png)

![](https://github.com/SimleCp/BBS/blob/master/ScreenShot/4.png)

注: 运行`BBS-iOS`, 如果你用的是我的服务器地址, 在帖子里面有很大的图片情况下, 进入帖子详情的时候, 会卡一会, 服务器水管小. 没办法 T-T

#### 已完成的接口

注册
登录
所有帖子列表
论坛列表
帖子详情
帖子评论列表
评论帖子
发布帖子
上传图片
获取当前用户信息
...

## 使用方式

### 让iOS端跑起来

1. clone 和 pod install, 项目是基于cocoapods的.

2. 安装好后直接运行即可.

注: 

用这个地址, 需要把BBS-Server clone到本地, 自己运行起来, 也就是用你的mac当服务器

```
let httpAdress = "http://0.0.0.0:8181/"
```

用这个地址, 直接运行BBS-iOS项目即可
```
let httpAdress = "http://swift520.com:8181/"

```

配置文件在`BBS-iOS/Tool.swift`

### 让服务端跑起来

1. clone项目, 并且cd到项目目录, `swift build`编译项目(如果你的终端没有翻墙, 那么这个过程会很慢)
2. 编译完成, 会出现`Linking ./.build/x86_64-apple-macosx10.10/debug/BBS-Server`这样的log输出. 直接拷贝`./.build/x86_64-apple-macosx10.10/debug/BBS-Server`, 运行即可.

过程如图:

![](https://github.com/SimleCp/BBS/blob/master/images/0.png)

3. 安装本地MySql, 请看此文章 [点我](http://cxp.im/2017/10/07/Swift%20Perfect%20Mac%E6%9C%AC%E5%9C%B0%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE/)
只需要看安装部分即可, 安装完成后, 命令启动数据库, 终端输出`Starting MySQL  . SUCCESS!`即可.

4. 安装Navicat Premium的Mac App, 请自行网上搜索安装.

5. 用Navicat Premium, 新建mysql连接, 连接成功后, 打开数据库. 按下面的图, 新建一个bbs的数据库, 参数请务必和我图上的一致. 然后导入`bbs.sql`文件即可. 见下方图片.

![](https://github.com/SimleCp/BBS/blob/master/images/1.png)

![](https://github.com/SimleCp/BBS/blob/master/images/2.png)

![](https://github.com/SimleCp/BBS/blob/master/images/3.png)

![](https://github.com/SimleCp/BBS/blob/master/images/4.png)

![](https://github.com/SimleCp/BBS/blob/master/images/5.png)

6. 导入sql成功后, 在iOS端的`BBS-iOS/Tool.swift`切换为`let httpAdress = "http://0.0.0.0:8181/"`

7. 重新运行`BBS-Server`和`BBS-iOS`项目. 现在你用的就是你mac上的本地数据库了.




