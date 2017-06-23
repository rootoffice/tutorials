### 目录操作
* `cd` 变换目录
* `pwd` 显示当前工作路径
* `mkdir` 创建新的空目录
* `rmdir` 删除一个空目录
* `ls -al` 检查文件或目录的相关信息

#### 例子
    alpha@AlphaCat:~/tutorial$ cd ~
    alpha@AlphaCat:~$ pwd
    /home/alpha
    alpha@AlphaCat:~$ cd /etc
    alpha@AlphaCat:/etc$ pwd
    /etc
    alpha@AlphaCat:/etc$ cd
    alpha@AlphaCat:~$ mkdir user
    alpha@AlphaCat:~$ cd ./user
    alpha@AlphaCat:~/user$ pwd
    /home/alpha/user
    alpha@AlphaCat:~$ rmdir ./user/
    alpha@AlphaCat:~$ cd ./user
    bash: cd: ./user: 没有那个文件或目录
### 文件操作
* `cp` 复制文件或目录
* `mv` 移动文件或目录或更名
* `rm` 移除文件或目录

#### 例子
    alpha@AlphaCat:~/joke$ cp page.html page.html.back
    alpha@AlphaCat:~/joke$ ls
    page.html  page.html.back
    alpha@AlphaCat:~/joke$ mv page.html.back mypage.html
    alpha@AlphaCat:~/joke$ ls
    mypage.html  page.html
    alpha@AlphaCat:~/joke$ rm -i page.html mypage.html
    rm：是否删除普通文件 'page.html'？ y
    rm：是否删除普通文件 'mypage.html'？ y
    alpha@AlphaCat:~/joke$ ls -l
    总用量 0

[参考文献1](http://cn.linux.vbird.org/linux_basic/0220filemanager_1.php)  
[参考文献2](http://cn.linux.vbird.org/linux_basic/0220filemanager_2.php)
