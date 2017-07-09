## pip源配置
pip源配置文件可以放置的位置：

Linux/Unix:
/etc/pip.conf
~/.pip/pip.conf
~/.config/pip/pip.conf

Mac OSX:
~/Library/Application Support/pip/pip.conf
~/.pip/pip.conf
/Library/Application Support/pip/pip.conf

Windows:
%APPDATA%\pip\pip.ini
%HOME%\pip\pip.ini
C:\Documents and Settings\All Users\Application Data\PyPA\pip\pip.conf (Windows XP)
C:\ProgramData\PyPA\pip\pip.conf (Windows 7及以后) 

目前收集的比较好的镜像地址有：

    http://pypi.v2ex.com/simple/
    http://pypi.douban.com/simple/
    http://mirrors.aliyun.com/pypi/simple/

直接修改配置的方法：

windows系统

在用户文件夹下创建pip目录，并在pip目录下创建pip.in文件（%HOMEPATH%pippip.ini），文件中添加如下内容：

[global]
trusted-host=mirrors.aliyun.com
index-url=http://mirrors.aliyun.com/pypi/simple/

备注：index-url即源地址，trusted-host为源地址的域名，由于国内的源镜像都为使用https协议，所以如果不添加信任域就会报：

linux系统
不改配置文件，每次手动指定：

pip install -i http://<mirror>/simple <package>

例如

pip install -i http://pypi.douban.com/simple simplejson

可以配置如下：
[global]
index-url = http://pypi.douban.com/simple #豆瓣源，可以换成其他的源
trusted-host = pypi.douban.com            #添加豆瓣源为可信主机，要不然可能报错
disable-pip-version-check = true          #取消pip版本检查，排除每次都报最新的pip
timeout = 120
