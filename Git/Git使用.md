# Git

[toc]

## 1.版本控制

版本控制、版本迭代、修改历史

本地版本控制

集中版本控制

分布式版本控制

Git 和 SVN 区别:

- SVN是集中式版本控制系统，版本库是集中放在中央服务器的，集中十版本控制系统必须联网才能工作
- Git是分布式版本控制系统，没有中央服务器，每个人的电脑就是一个完整的版本库，工作时不需要联网

## 2.Git的历史

## 3.Git环境配置

### Git安装

git 官网 [https://git-scm.com/], 下载对应操作系统的版本

太慢可以找镜像
[http://npm.taobao.org/mirrors/git-for-windows/]

卸载: 清除环境变量 -> 卸载软件
安装: 默认下一步安装(可选择路径)  默认文本编辑器可选(默认是Vim)

Git Bash: Unix和Linux风格的命令行，使用最多
Git CMD: Windows风格命令行
Git GUI: 图形界面的Git

### Linux基本命令

- cd    改变目录
- cd .. 退回上一级目录(cd后面有空格，没有会报错)
- pwd   显示当前目录
- ls    显示目录(蓝色文件夹，白色文件)
- ll    更详细地显示目录
- touch 在当前目录创建一个新的文件
- rm    删除一个文件
- mkdir 创建一个目录(文件夹)
- rm -r 删除一个文件夹  rm -r src
    rm -rf /    切勿在Linux中尝试，删除电脑中全部文件
- mv    移动目标    mv index.html src
- reset 重新初始化终端(清屏)
- clear 清屏(Windows下为cls)
- history 查看命令历史
- help  帮助
- exit  退出
- #表示注释

### Git配置

- git config -l 查看git配置
- git config --system --list    查看系统配置
- git config --global --list    查看本地配置(比如用户名、邮箱)

### Git配置用户名和邮箱(必须配置)

系统配置    Git\etc\gitconfig
用户配置    C:\Users|Administrator\.gitconfig

删除配置: 清空用户配置文件

配置用户名和邮箱:

```js
git config --global user.name "huli"
git config --global user.email "2969054528@qq.com"
```

配置环境变量只是为了能够全局使用，默认会自动配置

## 4.Git基本理论(核心)

Workspace: 工作区，本地存放项目代码的地方
Index/Stage: 暂存区，用于临时存放你的改动，事实上只是一个文件，保存即将提交的文件列表信息
Repository: 仓库区，就是安全存放数据的位置，这里有所有的版本数据，其中HEAD指向最新放入仓库的版本
Remote: 远程仓库，托管代码的服务器

## 5.Git项目搭建

本地仓库搭建    git init
克隆远程仓库到本地  git clone url

## 6.Git文件操作

### 文件四种状态

Untracked: 未跟踪，文件在文件夹中，但是没有加入git库(比如本地新建的文件)，通过**git add**改变状态为Staged
Unmodify: 文件已入库，未修改，即版本库和文件夹中完全一致，如果被修改则变成Modified，如果被**git rm**则变成Untracked文件
Modified: 文件已修改，仅仅是修改，没有进行其他操作，可以通过**git add**进入Staged暂存状态，使用**git checkout(从库中取出文件，覆盖当前修改)**放弃修改，返回到Unmodify状态
Staged: 暂存状态，执行**git commit**则将修改同步到库中，此时库中的文件和本地文件又变成一致的，文件变为Unmodify状态，执行**git reset HEAD filename**取消暂存，文件状态变成Modified

- git status [filename] 查看指定文件状态
- git status    查看所有文件状态
- git add .     添加所有文件到暂存区
- git commit -m'备注'   提交暂存区所有文件到本地仓库

有时候有些文件不需要纳入版本控制，提交时需要**忽略文件**，在主目录下建立 .gitignore 文件，文件规则如下:

- 忽略文件中的空行或以 # 开头的行会被忽视
- **(*)**通配符代表任意多个字符，**(?）)**问号代表一个字符，**([])**方括号代表可选字符范围，**({})**大括号代表可选字符串
- **(!)**感叹号表示例外规则，将不被忽视
- 名称最前面是一个路径分隔符 **(/)**，表示要忽略的文件在此目录下，而子目录中的文件不忽略
- 名称最后面是一个路径分隔符 **(/)**，表示忽略的是此目录下该名称的子目录，而非文件(默认文件和目录都忽略)

## 7.使用码云/Github

## 8.IDEA中集成Git

## 9.Git分支
