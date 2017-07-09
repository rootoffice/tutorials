## 查询记录
在使用Git提交了若干更新之后，又或者克隆了某个项目，想回顾下提交历史，我们可以使用`git log`命令查看。
* `git log`命令列出历史提交记录

```git
alpha@AlphaCat:~/joke$ git log
commit 3da88e892f9a0aeb8b3717b1b3679973cf13edea
Merge: 805f67e 3cf2c04
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:32:18 2017 +0800

    Merge branch 'alpha'

commit 805f67ee95b7e7e3e490b63861a03f0290f334c2
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:25:48 2017 +0800

    增加不同形容词

commit 3cf2c04eaaa9816e05131dfb44ebcee808d8d238
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:23:05 2017 +0800

    增加形容词

commit 40834f7eb8a48369b8341703bafad46fea34c8a9
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 20:19:38 2017 +0800
```

* `git log --oneline`选项来查看历史记录的简洁的版本，也可加`-number`表示显示总行数

```git
alpha@AlphaCat:~/joke$ git log --oneline
3da88e8 Merge branch 'alpha'
805f67e 增加不同形容词
3cf2c04 增加形容词
40834f7 增加内容
b542cd0 写了一个简单的HTML文档
e168f9d 重命名文档
5a73a16 第二次提交
48acc54 第一次提交
```

* `git log --decorate`除了显示`git log`的信息外还能显示分支信息或（ref names）


```git
alpha@AlphaCat:~/joke$ git log --decorate
commit 3da88e892f9a0aeb8b3717b1b3679973cf13edea (HEAD -> master)
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
```


* `git log --graph`查看历史中什么时候出现了分支、合并，开启了拓扑图选项

```git
alpha@AlphaCat:~/joke$ git log --graph --oneline
*   3da88e8 Merge branch 'alpha'
|\  
| * 3cf2c04 增加形容词
* | 805f67e 增加不同形容词
|/  
* 40834f7 增加内容
* b542cd0 写了一个简单的HTML文档
* e168f9d 重命名文档
* 5a73a16 第二次提交
* 48acc54 第一次提交
* 680056e 增加自己介绍
```

* `git log --reverse`来逆向显示所有日志

```git
alpha@AlphaCat:~/joke$ git log --reverse
commit 680056eca9bb6a7fdccebdc228a95bb00dbeb061
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 16:51:06 2017 +0800

    增加自己介绍

commit 48acc54560125ff13457d870622c3ce278fb02a2
Author: willem <rootoffice@sina.com>
Date:   Fri Jun 23 17:37:51 2017 +0800

    第一次提交
```

* `git log --author`查找指定用户的提交日志

```git
alpha@AlphaCat:~/joke$ git log --author=willem --oneline -5
3da88e8 Merge branch 'alpha'
805f67e 增加不同形容词
3cf2c04 增加形容词
40834f7 增加内容
b542cd0 写了一个简单的HTML文档
```

* `--since`和`--before`或`--until`和`--after`指定日期

```git
# 看Git项目中三周前且在四月十八日之后的所有提交
$ git log --oneline --before={3.weeks.ago} --after={2010-04-18} --no-merges
```
