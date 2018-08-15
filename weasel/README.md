weasel 是rime在windows下的发行版

## 初始安装

参考：[【小狼毫】Rime for Windows](https://github.com/rime/weasel)

    用戶詞庫、配置文件位於 %AppData%\Rime，可通過菜單中的「用戶文件夾」打開。

修改输入法的配置都需要改动此目录下的内容再重新布署。

于2018-08-07安装完成后，将配置目录备份起来。忽略 *.bin 文件及 *.userdb 目录。

在此默认配置中，没有五笔输入法，用快捷键Ctrl +`或F4切换输入方案。

安装完后，输入法切换时会有两个rime输入法，其中一个带有（TSF）字样，这个会在语言栏中多了一个“中”字样的位置，右键，会弹出的菜单，方便配置，所以可以在输入法配置中将另一个rime从列表中去除。

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


## 配置 

rime 输入法的配置文件都在所谓的用户文件夹中，在前述输入法菜单中有个用户文件夹，能直接在资源管理器中打开此目录，一般是 ~\AppData\Roaming\Rime 。另外还有一个程序文件夹，则是安装目录。rime输入法的配置是很重要的一方面，很多功能都是修改用户文件夹下的配置文件再重新布署实现的。

**以下用`$RIME_CONFIG`代指用户文件夹。**


配置文件是yaml格式，用空格组织结构，具体可以看语法。  
有一个注意点：区分空格和tab键的，缩进一定要用两个空格作为一层。  
还有一个规范：rime配置文件建议不要直接在原有的文件上修改。

    比如原有一个 `$RIME_CONFIG/build/default.yaml` 配置文件，当你要在此文件的基础上修改时，应该新建形如 `xxx.custom.yaml`的文件，用patch格式修改，对于此文件，则应修改
    `$RIME_CONFIG/default.custom.yaml`文件


#### 以下是具体一些功能的配置说明


***为了简便，约定以下涉及yaml的写法：***  
***1  最靠左的元素在真实的yaml文件中就是顶格的，也就是它的左边没有空格***  
***2  `...`代表零行或多行其它与主题无明显相关的配置项***  

- 控制方案选单中的可选项及顺序

方案选单里有多个方案时，通过`schema_list`控制，例如此处，想让五笔成为默认输入方案，就在 `$RIME_CONFIG/default.custom.yaml`文件中加上以下格式的内容：
```sh
patch:
    ...
  schema_list:
    - {schema: wubi86}
    - {schema: luna_pinyin_simp}
    ...
```




