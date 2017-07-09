## 标签管理
发布一个版本时，我们通常先在版本库中打一个标签（tag），这样，就唯一确定了打标签时刻的版本。将来无论什么时候，取某个标签的版本，就是把那个打标签的时刻的历史版本取出来。所以，标签也是版本库的一个快照。

Git的标签虽然是版本库的快照，但其实它就是指向某个commit的指针（跟分支很像对不对？但是分支可以移动，标签不能移动），所以，创建和删除标签都是瞬间完成的。

### 创建标签
* `git tag [tagname]`用于新建一个标签，默认为HEAD，也可以指定一个commit id

```git
alpha@AlphaCat:~/joke$ git tag v1.0
alpha@AlphaCat:~/joke$ git log --decorate
commit 3da88e892f9a0aeb8b3717b1b3679973cf13edea (HEAD -> master, tag: v1.0)
Merge: 805f67e 3cf2c04
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:32:18 2017 +0800

    Merge branch 'alpha'

commit 805f67ee95b7e7e3e490b63861a03f0290f334c2
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:25:48 2017 +0800

    增加不同形容词

commit 3cf2c04eaaa9816e05131dfb44ebcee808d8d238 (alpha)
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:23:05 2017 +0800

    增加形容词
alpha@AlphaCat:~/joke$ git tag v0.9 40834f7e
alpha@AlphaCat:~/joke$ git log --decorate
commit 3da88e892f9a0aeb8b3717b1b3679973cf13edea (HEAD -> master, tag: v1.0)
Merge: 805f67e 3cf2c04
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:32:18 2017 +0800

    Merge branch 'alpha'

commit 805f67ee95b7e7e3e490b63861a03f0290f334c2
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:25:48 2017 +0800

    增加不同形容词

commit 3cf2c04eaaa9816e05131dfb44ebcee808d8d238 (alpha)
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:23:05 2017 +0800

    增加形容词

commit 40834f7eb8a48369b8341703bafad46fea34c8a9 (tag: v0.9)
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:19:38 2017 +0800
    增加内容
```

* `git tag -a`可以创建带有说明的标签，加上`-m`可指定说明文字

```git
alpha@AlphaCat:~/joke$ git tag -a v1.1 -m 'version 1.1released' HEAD
alpha@AlphaCat:~/joke$ git show v1.1
tag v1.1
Tagger: willem <rootoffice@sina.com>
Date:   Sat Jun 24 09:41:12 2017 +0800

version 1.1released

commit d2fdf0ceed7c943858e39951d0b90ced3038d4dd
Author: willem <rootoffice@sina.com>
Date:   Sat Jun 24 09:39:43 2017 +0800

    加入一行文字

diff --git a/page b/page
index e44d934..eef15ad 100644
--- a/page
+++ b/page
@@ -8,5 +8,6 @@
 I am a good smart and cute boy.
 I come from China.
 I love my hometown.
+This is a web page.
 </body>
 </html>
```

* `git tag -s`私钥签名一个标签，签名采用PGP签名，必须首先安装gpg（GnuPG）

```git
$ git tag -s v0.2 -m "signed version 0.2 released" fec145a
```

* git tag查看所有标签

```git
alpha@AlphaCat:~/joke$ git tag
v0.9
v1.0
v1.1
```

### 操作标签
* `git push origin [tagname]`可以向远程推送一个本地标签；

* `git push origin --tags`可以推送全部未推送过的本地标签；

* `git tag -d [tagname]`可以删除一个本地标签；

* `git push origin :refs/tags/[tagname]`可以删除一个远程标签。
