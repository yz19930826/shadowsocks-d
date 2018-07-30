[toc]
## 写在前面的话
这篇文章建立在[Vultr搭建SS(ShadowSocks)教程-超详细](http://www.hellojava.club/article/27)上，采用的是Vultr VPS,搭建SS的话看这篇文章。

此外，我教程的东西都是经过自己实践验证的，不会有**不能用的，不可以的**还发博客来耽误大家的时间。

## 实现效果
先把实现效果展示一下，确定是自己想要的东西再往下看，毕竟时间宝贵。

### 搭建前
ping值

![](http://p1hy9syru.bkt.clouddn.com/18-1-5/13348252.jpg)

观看YouTube清晰度

1080无压力，1440就有压力了，如下图：
![](http://p1hy9syru.bkt.clouddn.com/18-1-5/61947620.jpg)

![](http://p1hy9syru.bkt.clouddn.com/18-1-5/77260076.jpg)

### 搭建后
ping，可以看出，优化的效果不是很大，毕竟访问个网络要绕地球一大圈。
![](http://p1hy9syru.bkt.clouddn.com/18-1-5/85392891.jpg)

观看YouTube的清晰度

1440p已经无压力了，如下图：
![](http://p1hy9syru.bkt.clouddn.com/18-1-5/11360812.jpg)

2160P会有卡顿，当然也和我的无线渣渣网速有关系，如下图：
![](http://p1hy9syru.bkt.clouddn.com/18-1-5/74654298.jpg)

我的网络状况，如下图所示，10M都没到好么。。就算不翻墙这个网速能看2160p已经很好了：
![](http://p1hy9syru.bkt.clouddn.com/18-1-5/47453307.jpg)


## 实现环境
1. VPS 采用的是Vultr
2. 操作系统:CentOS7
3. 节点位置：东京
4. 本机位置：北京

## 实现条件
需要VPS的架构为KVM，[openVZ架构](https://baike.so.com/doc/1129853-1195239.html)是不行的.具体细节请[戳我](http://banwagong.cn/ovz-kvm.html)

但是请放心，[Vultr](https://www.vultr.com/?ref=7295935)和搬瓦工都是KVM架构的，并且本教程的脚本可以自动检测架构，如果是openVZ架构会提示错误，并自动退出。

所以尽情尝试吧~



## 开始搭建

### 执行脚本
在Xshell中输入以下脚本：
```
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh
```

如下图所示，然后随便按一个键开始，接着耐心等待安装完成：
![](http://p1hy9syru.bkt.clouddn.com/18-1-5/23520745.jpg)

执行完毕之后，提示需要重启VPS，输入y，点回车，如下图：

![](http://p1hy9syru.bkt.clouddn.com/18-1-5/24631609.jpg)

这时候XShell会断开，没关系，等待片刻再尝试连接(XShell的重新连接在 **文件->重新连接**)~

重新连接成功之后，在XShell中输入以下命令，如果返回结果包含tcp_bbr，则安装成功：
```
lsmod | grep bbr
```
如下图所示：

![](http://p1hy9syru.bkt.clouddn.com/18-1-5/68031417.jpg)


## 以下为手动搭建SS（ShadowSocks）的用户需要执行的步骤

### 启动SS
因为刚才我们重启了VPS，因此SS服务可能关闭了，在XShell中输入以下命令，启动服务即可：

```
ssserver -c /etc/shadowsocks.json -d start
```
结果如下图：
![](http://p1hy9syru.bkt.clouddn.com/18-1-5/26127388.jpg)

### 配置防火墙
XShell中输入：
```
systemctl stop firewalld.service
```
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/27165290.jpg)


> 以上一键安装脚本来自于秋水逸冰，感谢