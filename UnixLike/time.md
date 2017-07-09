## 问题原因
Windows系统直接将电脑的物理时间当作本地时间显示，而Linux系统将电脑的物理时间当作UTC时间，会根据所在时区对时间进行调整后再显示，因此造成了两个系统显示的时间不一致。
## 解决办法
1.对于老版本的Ubuntu系统，把文件`/etc/default/rcS`中的`UTC=yes`修改成`UTC=no`可以让系统直接显示物理时间。

在新版本的系统中，rcS文件的设置会被忽略，代替它的是`/etc/adjtime`文件。
在`/etc/adjtime`文件的第三行中，只要将UTC改为LOCAL即可让Linux系统直接显示物理时间，不对时间进行调整。

2.如果不想手动修改adjtime文件，可以使用`hwclock`命令进行设置

    $ sudo hwclock -w --localtime
执行该命令后adjtime文件的第三行会自动变为LOCAL，然后在将系统时间调整为正确的时间即可。

3.在薄荷开源网上看到的解决办法，只需执行一条命令而且不需要超级权限

    $ timedatectl set-local-rtc 1
    $ cat adjtime
    0.0 0 0
    0
    LOCAL
