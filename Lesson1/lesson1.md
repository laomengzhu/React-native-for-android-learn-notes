# React native for android 学习笔记一：环境搭建（Windows）

## 1、安装JDK并配置环境变量

  Android SDK依赖于Java运行环境，所以我们需要配置好Java环境

### 安装JDK

  JDK下载：http://www.oracle.com/technetwork/java/javase/downloads/index.html

  下载完成后双击exe文件安装即可，假如安装目录为：D:\ADT\Java\jdk1.8.0_60；

### 配置Java环境变量

  安装完成后，右击“我的电脑”，点击“属性”，点击“高级系统设置”，点击“环境变量”，在系统变量中设置一下变量：

  JAVA_HOME：指明JDK安装路径，就是刚才安装时所选择的路径D:\ADT\Java\jdk1.8.0_60，此路径下包括lib，bin，jre等文件夹。

  PATH：Path使得系统可以在任何路径下识别java命令，设为：%JAVA_HOME%/bin;%JAVA_HOME%/jre/bin

  CLASSPATH：CLASSPATH为java加载类(class or lib)路径，只有类在classpath中，java命令才能识别，设为：.;%JAVA_HOME%/lib/dt.jar;%JAVA_HOME%/lib/tools.jar (要加.表示当前路径)，%JAVA_HOME%就是引用前面指定的JAVA_HOME；

### 测试Java环境

  打开命令行工具，输入“java -version”，出现如下画面则说明环境变量配置成功；

  ![Screenshot](https://raw.githubusercontent.com/xiaolifan/React-native-for-android-learn-notes/master/Lesson1/images/java-environment-test.png)

## 2、安装Android SDK并配置环境变量

## 3、安装node js

## 4、安装React native

## 5、创建并运行Hello Word
