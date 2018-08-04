## 写在前面的话 
搭建SS请看这篇文章：[Vultr搭建SS(ShadowSocks)教程-超详细](http://www.hellojava.club/article/27)

很多朋友对技术不是很熟悉，想使用一键搭建，但还希望多端口的形式，这篇文章就是解决这个问题。

## 前提

1. 已经使用一键搭建完成ss的搭建
2. 没了


## 开始修改成多端口

很简单，两分钟即可，连接上vultr，在xshell中输入
```
vi /etc/shadowsocks.json
```
![](http://p1hy9syru.bkt.clouddn.com/18-2-11/24766507.jpg)

回车，点击键盘i键，左下角会出现insert，如下图：
![](http://p1hy9syru.bkt.clouddn.com/18-2-11/56974627.jpg)

上下左右键将光标移动到password处，将其修改成下面这种形式(端口和密码自己设置，多少个随意，端口必须大于1023，小于65535。保证格式正确，符号必须是英文输入法下的！！)：
```
    "port_password":{
        "2018":"12345678",
        "2019":"12345678"
    },
```
总体如下图：
![](http://p1hy9syru.bkt.clouddn.com/18-2-11/42798537.jpg)

点击esc键，输入:wq保存退出。

接着输入命令重启ss服务：
```
ssserver -c /etc/shadowsocks.json -d restart
```

如图：
![](http://p1hy9syru.bkt.clouddn.com/18-2-11/58820338.jpg)

成功，尝试用不同的端口和密码连接吧~


## 搭建有问题或者想了解更多？

请看：[哈喽爪哇-让技术更有价值的传播](http://www.hellojava.club/)

