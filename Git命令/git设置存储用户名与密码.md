# git设置存储用户名与密码



刚玩github 每次push的时候都需要输用户名和密码，真心很烦......

在网上找了很多方法像什么改成ssh的都会出错，是我太弱吧！！！！



最终找到一种方法解决问题。

git是没有记录有户名和密码的，只能自己设置，在bash命令行设置，代码如下：

```
git config --global user.name "myusername"
git config --global user.email "myusername@myemaildomain.com"
git config --global credential.helper wincred
```

然后再根据正常push输一次用户名和密码，git就会存储下来；

假如出现错误：

```
git: 'credential-cache' is not a git command. See 'get --help'.
```

这是因为最后一行输入有错；

最后一行是根据版本不同，命令就不同。

下面有别的版本的；

```
git config --global credential.helper winstore
git config --global credential.helper cache
```

都试一下，总有一个对的，没有的话，网上百度一下吧，找一下新版本的命令。