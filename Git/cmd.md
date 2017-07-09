### 创建仓库
使用`git init`命令来初始化一个Git仓库

```git
# 创建一个空的仓库
alpha@AlphaCat:~$ mkdir ./joke
alpha@AlphaCat:~$ cd ./joke
alpha@AlphaCat:~/joke$ git init
初始化空的 Git 仓库于 /home/alpha/joke/.git/

# 将已有文件目录初始化为仓库
alpha@AlphaCat:~$ git init ./tutorials/
初始化空的 Git 仓库于 /home/alpha/tutorials/.git/
```

### 基本操作
Git的工作就是创建和保存你的项目的快照及与之后的快照进行对比。
* `git add`命令可将该文件修改添加到缓存区

```
# 可以使用git add .命令来添加当前项目的所有文件
alpha@AlphaCat:~/joke$ git add .
alpha@AlphaCat:~/joke$ git status
位于分支 master
初始提交
要提交的变更：
  （使用 "git rm --cached <文件>..." 以取消暂存）
	新文件：   me.md
```

* `git stash`藏匿操作需要修改的跟踪文件和阶段的变化
  > 藏匿的变化列表通过使用 git stash list命令，
  执行git stash pop 命令，它会从堆栈中删除的变化，并把它放在当前工作目录

* `git status`命令用于查看项目的当前状态

```git
alpha@AlphaCat:~/joke$ vim page.html
alpha@AlphaCat:~/joke$ git status
位于分支 master
未跟踪的文件:
  （使用 "git add <文件>..." 以包含要提交的内容）
	page.html
提交为空，但是存在尚未跟踪的文件（使用"git add"建立跟踪）
alpha@AlphaCat:~/joke$ git status -s
?? page.html
alpha@AlphaCat:~/joke$ git add page.html
alpha@AlphaCat:~/joke$ git status -s
A  page.html
# "AM"状态意思是，文件在我们将它添加到缓存之后又有改动
alpha@AlphaCat:~/joke$ vim page.html
alpha@AlphaCat:~/joke$ git status -s
AM page.html
```

* `git diff`来查看执行`git status`的结果的详细信息
> * 尚未缓存的改动：git diff
  * 查看已缓存的改动： git diff --cached
  * 查看已缓存的与未缓存的所有改动：git diff HEAD
  * 显示摘要而非整个 diff：git diff --stat

```git
alpha@AlphaCat:~/joke$ git diff
diff --git a/page.html b/page.html
index c202b80..785b874 100644
--- a/page.html
+++ b/page.html
@@ -1 +1,2 @@
+# git add后又有改动
 I am a good boy.
alpha@AlphaCat:~/joke$ git diff --cached
diff --git a/page.html b/page.html
new file mode 100644
index 0000000..c202b80
--- /dev/null
+++ b/page.html
@@ -0,0 +1 @@
+I am a good boy.
alpha@AlphaCat:~/joke$ git diff HEAD
diff --git a/page.html b/page.html
new file mode 100644
index 0000000..785b874
--- /dev/null
+++ b/page.html
@@ -0,0 +1,2 @@
+# git add后又有改动
+I am a good boy.
alpha@AlphaCat:~/joke$ git diff --stat
 page.html | 1 +
 1 file changed, 1 insertion(+)
```

* `git commit`将缓存区修改内容添加到仓库中

```git
# 使用-m选项以在命令行中提供提交注释
# 把第一次的git add提交
alpha@AlphaCat:~/joke$ git commit -m '第一次提交'
[master 48acc54] 第一次提交
 1 file changed, 1 insertion(+)
 create mode 100644 page.html
alpha@AlphaCat:~/joke$ git status -s
 M page.html
alpha@AlphaCat:~/joke$ git add page.html
alpha@AlphaCat:~/joke$ git status -s
M  page.html
alpha@AlphaCat:~/joke$ git commit -m '第二次提交'
[master 5a73a16] 第二次提交
 1 file changed, 1 insertion(+)
```
> 如果你觉得git add提交缓存的流程太过繁琐，Git也允许你用-a选项跳过这一步。

* `git reset`命令用于取消已缓存的内容
* `git rm`会将条目从缓存区中移除
  > 默认情况下，`git rm file`会将文件从缓存区和你的硬盘中（工作目录）删除。如果你要在工作目录中留着该文件，可以使用`git rm --cached`

```
alpha@AlphaCat:~/joke$ ls
me.md  page.html
alpha@AlphaCat:~/joke$ git status
位于分支 master
无文件要提交，干净的工作区
alpha@AlphaCat:~/joke$ git rm me.md
rm 'me.md'
alpha@AlphaCat:~/joke$ ls
page.html
alpha@AlphaCat:~/joke$ git rm --cached page.html
rm 'page.html'
alpha@AlphaCat:~/joke$ ls
page.html
alpha@AlphaCat:~/joke$ git status -s
D  me.md
D  page.html
?? page.html
```

* `git mv`命令做得所有事情就是`git rm --cached`命令的操作，重命名磁盘上的文件，然后再执行 git add 把新文件添加到缓存区。

```git
alpha@AlphaCat:~/joke$ git add page.html
alpha@AlphaCat:~/joke$ git mv page.html page
alpha@AlphaCat:~/joke$ ls
page
alpha@AlphaCat:~/joke$ git status -s
D  me.md
R  page.html -> page
```
