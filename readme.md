> Fork 自 GFW.Press，自己魔改版本


## 一、客户端

Windows 请访问 http://gfw.press/GFW.Press.msi 下载客户端安装包 配置填写完成，点击“确定”按钮

Windows 下有闪退问题的可以直接下载JDK，运行 gfw.press_fat.jar，自己安装JDK 需要替换 JCE，具体请 Google

Linux 使用项目根目录下的 gfw.press_fat.jar

<img width="614" alt="server" src="https://cloud.githubusercontent.com/assets/13043245/15628329/f60b8a9a-2530-11e6-9d93-424f7ded2242.png">


<img width="585" alt="client" src="https://cloud.githubusercontent.com/assets/13043245/15628331/fcd97332-2530-11e6-9984-31a60b1fa375.png">

<img width="603" alt="help" src="https://cloud.githubusercontent.com/assets/13043245/15628337/2d647b50-2531-11e6-9682-07e8909e97c0.png">


## 二、服务器

### 第一步： copy gfw.press_fat.jar 到任意目录

### 第二步：安装 JDK

``` sh
yum install java-1.8.0-openjdk.x86_64 -y ;
```

**注意: sun jdk 由于美国进出口软件法律限制，需替换其加密相关jar， [下载地址点我](http://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html)
，使用教程请自行 Google**

### 第三步：安装代理软件

``` sh
yum install squid -y ; 或者 yum instsall 3proxy -y ;
``` 

### 第四步：在 gfw.press_fat.jar 同级目录创建 user.txt(服务端)/client.json(客户端)

user.txt 每行表示一个帐号，由 端口号+空格+密码 组成，密码长度至少8位，必需包含大小写字母和数字

### 第五步：运行

``` sh
java -Dfile.encoding=utf-8 -Dsun.jnu.encoding=utf-8 -Duser.timezone=Asia/Shanghai -Xmn128M -Xms128M -Xmx256M -jar gfw.press_fat.jar [server/client/online]
```

**-Xmn128M -Xms128M -Xmx256M 三个参数根据自己服务器设置，意义自行 Google，
gfw.press_fat.jar 后面可选三个参数 server、client、online，
建议将 gfw.press_fat.jar 到其前面的命令设置别名，以下为样例**

``` sh
# ~/.bashrc
alias gfw="java -Dfile.encoding=utf-8 -Dsun.jnu.encoding=utf-8 -Duser.timezone=Asia/Shanghai -Xmn128M -Xms128M -Xmx256M -jar gfw.press_fat.jar"
# 执行命令
gfw server
gfw client
gfw online
```


