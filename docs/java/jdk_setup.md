# jdk的安装与配置

## 下载

### 下载页面

http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

选择`Java SE Development Kit 8u131`下的`Accept License Agreement`同意下载协议，然后可选择自己的系统和对应版本进行下载。

## 安装

### windows

以64位为例，下载到的jdk安装包为`jdk-8u131-windows-x64.exe`，双击安装，选择安装位置（通常默认）后一路下一步直至完成。由于windows安装jdk后会在控制面板有java的控制项，大多数情况下并不需要配置环境变量。打开cmd,执行`java -version`,如正常输出java版本信息则安装完成。

#### 环境变量

打开`控制面板\系统和安全\系统`，点击`高级系统设置>高级>环境变量`，在系统变量下`新建`变量`JAVA_HOME`，值为`C:\Program Files\Java\jdk1.8.0_131`。

新建变量`classpath`，值为`.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar`。

编辑`path`,在最前面添加`%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;`

### linux

以64位centos为例，下载的jdk压缩包为`jdk-8u131-linux-x64.tar.gz`，将其解压到`/opt/jdk1.8`,然后编辑`/etc/profile`,在文件最后添加以下

```profile
export JAVA_HOME=/opt/jdk1.8
export JRE_HOME=/opt/jdk1.8/jre
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib:$CLASSPATH
export PATH=$JAVA_HOME/bin: $PATH
```

在终端运行`java -version`,如输出jdk版本信息则配置成功。



