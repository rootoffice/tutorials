## 在Ubuntu上安装Octave，两种方法：
 
* 从仓库中安装
```bash
$ sudo apt-add-repository ppa:octave/stable
$ sudo apt-get update
$ sudo apt-get install octave
```
* 从源码编译安装
去ftp://ftp.gnu.org/gnu/octave/ 下载最新的octave源代码：
我下载的版本是4.2.1：
$ cd /tmp
$ wget ftp://ftp.gnu.org/gnu/octave/octave-4.0.2.tar.gz
解压：
$ tar xf octave-4.0.2.tar.gz
安装构建依赖：
$ sudo apt-get build-dep octave
我在执行上面命令时出现了如下错误：
E: You must put some 'source' URIs in your sources.list
解决方法是编辑 /etc/apt/sources.list 文件，去掉deb-src行之前的#号注释。
编辑安装octave：
$ cd octave-4.0.2/
$ ./configure
$ make 
$ sudo make install
运行octave：
$ sudo octave
