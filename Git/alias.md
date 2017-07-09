## 配置别名
如果觉得这些git命令过于繁琐，可以设置别名

    $ git config --global alias.[aliasname] [cmdname]

例如
```git
$ git config --global alias.st status
$ git config --global alias.co checkout
$ git config --global alias.ci commit
$ git config --global alias.br branch

$ git config --global alias.unstage 'reset HEAD'
$ git config --global alias.last 'log -1'
```

配置Git的时候，加上｀是针对当前用户起作用的，如果不加，那只针对当前的仓库起作用。每个仓库的Git配置文件都放在`.git/config`文件中

## 删除别名
要删除别名，直接把对应配置文件的行删掉即可
