### 下载及安装
Debian/Ubuntu  
`# apt-get install git`

Git via Git  
`git clone https://github.com/git/git`
### Git 配置
`Git`提供了一个叫做`git config`的工具，专门用来配置或读取相应的工作环境变量。
这些环境变量，决定了`Git`在各个环节的具体工作方式和行为。这些变量可以存放在以下三个不同的地方：
* `/etc/gitconfig`文件：系统中对所有用户都普遍适用的配置。若使用`git config`时用`--system`选项，读写的就是这个文件。
* `~/.gitconfig`文件：用户目录下的配置文件只适用于该用户。若使用`git config`时用`--global`选项，读写的就是这个文件。
* 当前项目的Git目录中的配置文件（也就是工作目录中的`.git/config`文件）：这里的配置仅仅针对当前项目有效。每一个级别的配置都会覆盖上层的相同配置，所以`.git/config`里的配置会覆盖`/etc/gitconfig`中的同名变量。

```git
# 配置个人信息
alpha@AlphaCat:~$ git --version
git version 2.7.4
alpha@AlphaCat:~$ git config --global user.name 'willem'
alpha@AlphaCat:~$ git config --global user.email rootoffice@sina.com
alpha@AlphaCat:~$ git config --global core.editor vim
alpha@AlphaCat:~$ git config --global color.ui auto
# 查看配置
alpha@AlphaCat:~$ git config --list
user.name=willem
user.email=rootoffice@sina.com
core.editor=vim
color.ui=auto
alpha@AlphaCat:~$ cat ./.gitconfig
[user]
	name = willem
	email = rootoffice@sina.com
[core]
	editor = vim
[color]
	ui = auto
```

### Git远程仓库
要添加一个新的远程仓库可以将Github为例作为远程仓库，由于你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以我们需要配置验证信息
```git
# 生成SSH Key
alpha@AlphaCat:~$ ssh-keygen -t rsa -C "rootoffice@sina.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/home/alpha/.ssh/id_rsa):
Your identification has been saved in /home/alpha/.ssh/id_rsa.
Your public key has been saved in /home/alpha/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:xxxxxxxxxx rootoffice@sina.com
The key's randomart image is:
xxxxxxxxx
alpha@AlphaCat:~$ cat ./.ssh/id_rsa.pub
xxxxxxxxxxx
# 验证成功连上Github。
alpha@AlphaCat:~$ ssh -T git@github.com
Warning: Permanently added the RSA host key for IP address '192.30.255.112' to the list of known hosts.
Hi sinaemail! You've successfully authenticated, but GitHub does not provide shell access.
```

### 版本库
工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库，Git管理的是修改

Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD
