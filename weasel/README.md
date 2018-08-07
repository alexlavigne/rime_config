weasel 是rime在windows下的发行版

## 初始安装

参考：[【小狼毫】Rime for Windows](https://github.com/rime/weasel)

    用戶詞庫、配置文件位於 %AppData%\Rime，可通過菜單中的「用戶文件夾」打開。

修改输入法的配置都需要改动此目录下的内容再重新布署。

于2018-08-07安装完成后，将配置目录备份起来。忽略 *.bin 文件及 *.userdb 目录。

在此默认配置中，没有五笔输入法，用快捷键Ctrl +`或F4切换输入方案。

安装完后，输入法切换时会有两个rime输入法，其中一个带有（TSF）字样，这个会多一个菜单，方便配置，所以可以在输入法配置中将另一个rime从列表中去除。

*注：从某个win10版本开始，这个删除的方法有点绕，需要直接打开控制面板-语言 在win7风格下面的选择中才可以只删除某一个rime输入法*

## 安装五笔输入法

参考：[東風破 /plum/: Rime configuration manager and input schema repository](https://github.com/rime/plum)

*注：在输入法菜单中选择输入法设定，会看到一个获取更多输入方案，然而这个是过时的功能，使用起来会有问题。*

Download the [bootstrap bundle](https://github.com/rime/plum-windows-bootstrap/archive/master.zip), unpack the ZIP archive and run rime-install-bootstrap.bat for initial setup.

运行成功之后，会下载一个名为rime-install.bat的脚本，命令行中运行此脚本即可下载官方提供的输入方案。可用方案同样参考上方的链接。

安装五笔的命令为

```sh
./rime-install.bat wubi
```

显示成功后，在输入法菜单中选中重新布署，会出现 xx维护中 的提示，即为重新布署，一般很快。再打开菜单，可以看到可选输入方案中多了几种五笔相关的方案，选择想要的方案即可。本例中选择了一个五笔86和朙月拼音语句流。



