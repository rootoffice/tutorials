## Manual Installation
* Clone the repository:
```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
```

* Optionally, backup your existing ~/.zshrc file:

      cp ~/.zshrc ~/.zshrc.orig

* Create a new zsh configuration file

> You can create a new zsh config file by copying the template that we have included for you.

      cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc

* Change your default shell

      sudo chsh -s /bin/zsh [username]

* Initialize your new zsh configuration

>Once you open up a new terminal window, it should load zsh with Oh My Zsh's configuration.

## zsh主题

zsh的默认主题为robbyrussell，用了一段时间发现并不是那么好用，比如它不会把当前的工作路径全部展示出来，例如现在处于路径/home/zhu/go/src/MyProject中，此主题就只是显示最后路径，即MyProject，带来了一些不方便

因此想到换一个主题，用了cloud，有一朵云，挺好看，但是上面问题依然存在，看官网介绍zsh主题介绍，选择了ys主题，官网对其评价为：Clean, simple, compatible and meaningful.Tested on Linux, Unix and Windows under ANSI colors. It is recommended to use with a dark background.

## 修改方法

这些主题都在路径~/.oh-my-zsh/themes中，使某一主题生效的文件为~/.zshrc文件，找到ZSH_THEME="robbyrussell"一行（大概11行左右），把其注释掉，在下面添一行ZSH_THEME="ys"，之后关闭终端，再重启就好了。
> 注意：在=符号右边一定不要有空格，否则会报错找不到此主题，我就是在这里困了半个多小时。

oh-my-zsh插件

比较好用的是last-working-dir，此插件的作用是下一次打开终端时定位到之前的目录下，是一个很好用的插件。

使用方法同上，不同的是找到plugins=(git)这一行（大概55行左右），改为plugins=(git last-working-dir)，也是重启终端后生效。
