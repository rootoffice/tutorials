### 分支管理
每一种版本控制系统都以某种形式支持分支。使用分支意味着你可以从开发主线上分离开来，然后在不影响主线的同时继续工作。
* `git branch`列出已有分支
* `git branch -r`可以用来查看远程分支
* `git branch -a`查看所有分支
* `git branch [branchname]`创建分支
* `git checkout [branchname]`切换分支
* `git checkout -b [branchname]`创建并切换分支，相当前两个命令
* `git branch -d [branchname]`删除分支

```git
# *表示当前分支
alpha@AlphaCat:~/tutorials$ git branch alpha
alpha@AlphaCat:~/tutorials$ git branch
  alpha
* master
alpha@AlphaCat:~/tutorials$ git checkout alpha
M	Git/getstarted.md
切换到分支 'alpha'
alpha@AlphaCat:~/tutorials$ git branch
* alpha
  master
alpha@AlphaCat:~/tutorials$ git checkout -b beta
M	Git/getstarted.md
切换到一个新分支 'beta'
alpha@AlphaCat:~/tutorials$ git branch
  alpha
* beta
  master
alpha@AlphaCat:~/tutorials$ git branch -d beta
已删除分支 beta（曾为 e14eaf0）。
alpha@AlphaCat:~/tutorials$ git branch
  alpha
* master
```
> 在Git里，默认分支叫主分支，即master分支。HEAD严格来说不是指向提交，而是指向master，master才是指向提交的，所以，HEAD指向的就是当前分支，每次提交，master分支都会向前移动一步。

> 当我们创建新的分支，例如alpha时，Git新建了一个指针叫alpha，指向master相同的提交。在切换分支时把HEAD指向alpha，就表示当前分支在alpha上。

一旦某分支有了独立内容，你终究会希望将它合并回到你的主分支。
* `git merge [branchname]`合并[branchname]到当前分支上

```git
alpha@AlphaCat:~/joke$ git branch
* alpha
  master
alpha@AlphaCat:~/joke$ vim page
alpha@AlphaCat:~/joke$ git add page
alpha@AlphaCat:~/joke$ git status -s
M  page
alpha@AlphaCat:~/joke$ git commit -m "增加形容词"
[alpha 3cf2c04] 增加形容词
 1 file changed, 1 insertion(+), 1 deletion(-)
alpha@AlphaCat:~/joke$ git checkout master
切换到分支 'master'
alpha@AlphaCat:~/joke$ vim page
alpha@AlphaCat:~/joke$ git merge alpha
更新 40834f7..3cf2c04
error: Your local changes to the following files would be overwritten by merge:
	page
Please, commit your changes or stash them before you can merge.
Aborting
alpha@AlphaCat:~/joke$ git add page
alpha@AlphaCat:~/joke$ git commit -m "增加不同形容词"
[master 805f67e] 增加不同形容词
 1 file changed, 1 insertion(+), 1 deletion(-)
alpha@AlphaCat:~/joke$ git merge alpha
自动合并 page
冲突（内容）：合并冲突于 page
自动合并失败，修正冲突然后提交修正的结果。
alpha@AlphaCat:~/joke$ more page
<html>
<head>
<title>
开始
</title>
</head>
<body>
<<<<<<< HEAD
I am a good smart boy.
=======
I am a good cute boy.
>>>>>>> alpha
I come from China.
I love my hometown.
</body>
</html>
alpha@AlphaCat:~/joke$ vim page
alpha@AlphaCat:~/joke$ git add page
alpha@AlphaCat:~/joke$ git status -s
M  page
alpha@AlphaCat:~/joke$ git commit
[master 3da88e8] Merge branch 'alpha'
```
> 合并并不仅仅是简单的文件添加、移除的操作，Git也会合并修改
