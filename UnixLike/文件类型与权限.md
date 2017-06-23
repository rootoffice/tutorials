## 文件类型与权限
### 文件归属
* `u/U` 文件拥有者(owner)
* `g/G` 文件群组(group)
* `o/O` 其他人(others)

### 类型
* `d` 文件夹或目录
* `\-` 普通文件
* `l` 链接文件
* `b` 块设备或可供储存的接口设备，如硬盘
* `c` 串行端口设备，如键盘、鼠标

### 权限
* `r` 可读，数值4
* `w` 可写，数值2
* `x` 可执行，数值1

#### 例子
    alpha@AlphaCat:~$ ls -l /home/alpha/mnist
    total 68
    -rw-r--r-- 1 alpha alpha 2194 6月  21 10:09 BUILD
    -rw-r--r-- 1 alpha alpha 8707 6月  21 10:09 fully_connected_feed.py
    -rw-r--r-- 1 alpha alpha    1 6月  21 10:09 __init__.py
    -rw-r--r-- 1 alpha alpha 7309 6月  21 10:09 input_data.py
    -rw-r--r-- 1 root  root  6923 6月  21 10:12 input_data.pyc
    drwxr-xr-x 2 alpha alpha 4096 6月  21 10:16 Mnist_data
    -rw-r--r-- 1 alpha alpha 2537 6月  21 10:09 mnist_deep.py
    drwxr-xr-x 2 root  root  4096 6月  21 10:58 mnist_logs
    -rw-r--r-- 1 alpha alpha 5944 6月  21 10:09 mnist.py
    -rw-r--r-- 1 alpha alpha 1883 6月  21 10:09 mnist_softmax.py
    -rw-r--r-- 1 alpha alpha 4006 6月  21 10:09 mnist_with_summaries.py
    -rw-r--r-- 1 alpha alpha 3921 6月  21 10:09 README.md
> 注意：  
> drwxr-xr-x它们的顺便不能颠倒，某一位置为空(-)，则表示不具有相应的权限。文件可以针对归属用户，归属群组，其它用户用户或群组分别设定权限

#### 修改
* `chmod` 更改文件的权限，SUID，SGID，SBIT
* `chown` 更改文件的归属
* `chgrp` 更改文件的群组


    alpha@AlphaCat:~/mnist$ chmod u+x README.md
    alpha@AlphaCat:~/mnist$ ls -l /home/alpha/mnist/README.md
    -rwxr--r-- 1 alpha alpha 3921 6月  21 10:09 /home/alpha/mnist/README.md
    alpha@AlphaCat:~/mnist$ chmod 533 README.md
    alpha@AlphaCat:~/mnist$ ls -l /home/alpha/mnist/README.md
    -r-x-wx-wx 1 alpha alpha 3921 6月  21 10:09 /home/alpha/mnist/README.md
    alpha@AlphaCat:~/mnist$ sudo chown root:root README.md
    alpha@AlphaCat:~/mnist$ ls -l /home/alpha/mnist/README.md
    -r-x-wx-wx 1 root root 3921 6月  21 10:09 /home/alpha/mnist/README.md
    alpha@AlphaCat:~/mnist$ sudo chgrp root README.md
    alpha@AlphaCat:~/mnist$ ls -l README.md
    -rwxr-xr-- 1 alpha root 3921 6月  21 10:09 README.md

[参考文献](http://www.cnblogs.com/dutlei/archive/2012/11/20/2778327.html "Ubuntu完全教程，让你成为Ubuntu高手！")
