系统自带的 Python

```
$ which python
```

终端输出

```
/usr/bin/python
```

使用 Homebrew 安装最新的 Python2
为什么要使用 Homebrew 安装 Python?
总能下载到最新版本的 python

Homebrew 版的 python 包含了最新的 pip 和 setuptools 工具

安装步骤
首先需要安装苹果公司提供的免费 IDE 工具 Xcode,或者不安装 Xcode,只安装 Xcode 的命令行工具:

```
$ xcode-select --install
```

其次需要安装 Homebrew,安装方法参见官网http://brew.sh/

接着执行

```
$ brew update
```

通常在新安装 package 的时候都会更新 brew

最后，使用 brew 安装 python

```
$ brew install python2
```

会安装 python2.x 版本，截止到本文写作时安装的是 2.7.15 版本，可以使用如下命令查看 homebrew 版 python 相关信息:

```
$ which python2
```

终端输出

```
/usr/local/bin/python2
```

这是因为 Homebrew 会把 package 安装到/usr/local/Cellar 下，同时在/usr/local/bin 建立符号链接指向/usr/local/Cellar 下真正的 package 里的 bin。

用以下指令查看版本信息

```
python2 --version
```

终端输出

```
2.7.15
```

使用 Homebrew 安装最新的 Python3

```
$ brew install python3

$ which python3
```

终端输出

```
/usr/local/bin/python3
```
