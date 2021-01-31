>

### Git学习

#### 介绍

Git是什么？


Git是目前世界上最先进的分布式版本控制系统（没有之一）。


什么是版本控制系统？

版本控制是一种记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的系统。

* * *

#### 安装

##### 在Linux上安装Git

首先，你可以试着输入**git**，看看系统有没有安装Git：

```
$ git
The program 'git' is currently not installed. You can install it by typing:
sudo apt-get install git
```

像上面的命令，有很多Linux会友好地告诉你Git没有安装，还会告诉你如何安装Git。

若使用Debian或Ubuntu Linux，通过一条**sudo apt-get install git**就可以直接完成Git的安装，非常简单。

##### 在Mac OS X上安装Git

在 Mac 中，最好的安装方法就是 [Homebrew](https://brew.sh/)。如果您还没有在Mac 上安装它，请在 **终端** 运行以下命令：

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

如果您没有安装**命令行工具`(Command Line Tools)`**，则 Homebrew 安装可能需要更长一点时间。但它会自动处理，所以不用担心。请坐下来等到安装完成。

当您看到以下消息时，您会知道安装何时完成：


```
==> Installation successful!

==> Homebrew has enabled anonymous aggregate user behaviour analytics.
Read the analytics documentation (and how to opt-out) here:
  https://docs.brew.sh/Analytics.html

==> Next steps:
- Run `brew help` to get started
- Further documentation:
    https://docs.brew.sh
```

请运行以下命令来安装Git：

```
brew install git
```

##### 在Windows上安装Git

在Windows上使用Git，可以从Git官网直接[下载安装程序](https://git-scm.com/downloads)，然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

![image-20210131163343409](/Users/weipeng/Library/Application Support/typora-user-images/image-20210131163343409.png)

安装完成后，还需要最后一步设置，在命令行输入：

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。

注意**git config**命令的**--global**参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

* * *


#### 创建版本库

版本库又名仓库，英文名**repository**，你可以简单理解成一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

```
$ mkdir learngit
$ cd learngit
```

第二步，通过**git init**命令把这个目录变成Git可以管理的仓库：

```
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
```

Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），当前目录下多了一个`.git`的目录，这个目录是Git来跟踪管理版本库的，千万不要手动修改这个目录里面的文件，若改乱了，就把Git仓库给破坏了。

如果你没有看到`.git`目录，那是因为这个目录默认是隐藏的，用`ls -ah`命令就可以看见。

也可以在一个已经有东西的目录创建Git仓库

#### 把文件添加到版本库

首先这里再明确一下，所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Git也不例外。版本控制系统可以告诉你每次的改动，比如在第5行加了一个单词“Linux”，在第8行删了一个单词“Windows”。而图片、视频这些二进制文件，虽然也能由版本控制系统管理，但没法跟踪文件的变化，只能把二进制文件每次改动串起来，也就是只知道图片从100KB改成了120KB，但到底改了啥，版本控制系统不知道，也没法知道。

首先：在Git仓库目录下（子目录），编写一个`readme.txt`文件

其次用命令**git add**告诉Git，把文件添加到仓库：

```
$ git add readme.txt
```



