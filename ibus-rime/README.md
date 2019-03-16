ibus-rime是rime在linux下的发行版之一
本文基于archlinux下的操作，其他linux中的操作大体一致

## 初始安装

参考：[RimeWithIBus](https://github.com/rime/home/wiki/RimeWithIBus)
```sh
pacman -S ibus-rime
```

用户词库、配置文件位於 `$HOME/.config/ibus/rime`。
修改输入法的配置都需要改动此目录下的内容再重新布署。

ibus的相关操作参考:[IBus](https://wiki.archlinux.org/index.php/IBus)

于2019-03-1安装完成后，将配置目录备份起来。忽略 `*.bin` 文件及 `*.userdb` 目录。  

启动ibus后，打开输入法配置(ibus preference)，在Input Method标签页中，点击Add，在弹窗中选择Chinese，子菜单中会有rime,选择后就可以正常使用输入法了。

在此默认配置中，没有五笔输入法，用快捷键Ctrl +`或F4切换输入方案。
