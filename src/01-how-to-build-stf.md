#### 01-如何在本地调试stf项目

首先，可以去stf的开源项目阅读下其[主页](https://github.com/openstf/stf)内容。这里我将列出几点在我自身的本地环境搭建中的要点记录下。

第一点，要做的就是本地必须有node的开发环境，这里需要注意的是，作者特意提出必须是8版本的nodejs。主要是因为高版本的nodejs会导致stf的依赖会有问题。

第二点，在Mac下可以通过如下的命令直接安装stf的环境所需软件：

```sh
brew install rethinkdb graphicsmagick zeromq protobuf yasm pkg-config
```

第三点，然后在克隆下来stf的目录执行 npm install 来安装其所需的依赖；再使用 npm link 命令可以在任意的目录下使用stf命令。

第四点，在运行之前，先启动数据库。由于stf使用的是rethinkdb来作为数据库软件后台，调试的话我们直接在命令行下执行rethinkdb这条命令在前台运行即可。

第五点，启动stf。打开终端，在命令行中输入 stf local启动所有的stf模块。若没有任何异常出现的话，可以在浏览器中通过 http://127.0.0.1:7100 访问其服务。