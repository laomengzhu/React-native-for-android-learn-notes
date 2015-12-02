# 一：环境搭建（Windows）

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

### 安装Android SDK

到 http://developer.android.com/index.html 下载最新的SDK并安装；

### 配置环境变量

和Java环境变量的配置方法类似：

ANDROID_HOME：Android SDK的安装路径，比如：D:\ADT\Sdk

PATH：追加在最后面，D:\ADT\Sdk\tools;D:\ADT\Sdk\platform-tools;

## 3、安装node js

到Node.js官网：https://nodejs.org/en/ 下载最新版本Node.js并安装，由于国内网络环境的原因，我们在安装、更新Node.js模块的时候，经常遇到卡死的情况，我们这里把Node.js的源换成淘宝的源，方法很简单：找到Node.js安装目录，打开node_modules\npm\下的npmrc文件，加入“registry = https://registry.npm.taobao.org” 即可。

## 4、安装React native

打开“开始”菜单，找到Node.js目录，运行“Node.js command prompt”，输入“npm install -g react-native-cli”安装React native。至此，React native for android 的整个开发环境就搭建完毕了，下面就是试试吧！

![node-cmd](https://raw.githubusercontent.com/xiaolifan/React-native-for-android-learn-notes/master/Lesson1/images/node-cmd.png)

## 5、创建并运行Hello Word

### 创建HelloWord

运行“Node.js command prompt”，输入“react-native init HelloWord”，即可创建一个项目名为“HelloWord”的React native工程。

### 运行HelloWord

运行HelloWord之前，需要先安装并启动Genymotion模拟器。虽然官网说已经支持在Windows下运行Android项目了，但是我这边没有成功，所以还是使用老的方法：

1、首先启动React Native Server

react-native start

2、重新开一个终端(cmd), 切换到项目目录安装APP

cd android

gradlew.bat installDebug

不出意外，你应该能在模拟器中看到一个HelloWord的程序，点击运行就能看到以下画面：

![helloword](https://raw.githubusercontent.com/xiaolifan/React-native-for-android-learn-notes/master/Lesson1/images/helloword.png)

### 真机上运行

如果直接在真机上运行，会出现“unable download js bundle”错误，这是因为PC服务器端口和手机上的端口不对应所致的，你需要修改手机上的端口:

adb reverse tcp:8081 tcp:8081

然后摇晃手机，点击reload js重新加载js即可。

具体参照官方文档：http://facebook.github.io/react-native/docs/running-on-device-android.html#content

## 6、文档参照：

http://www.jianshu.com/p/3d716097fe08

https://facebook.github.io/react-native/docs/getting-started.html

http://blog.csdn.net/huanghm88/article/details/3965218
