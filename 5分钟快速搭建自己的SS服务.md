## 前置条件
1. 一台自己的VPS服务器，**系统选择为Centos7**（演示采用的Vultr，链接如下：[Vultr官方网站](https://www.vultr.com/?ref=7772826-4F)，新用户充值后貌似会送25美元）
2. 可以连接VPS的终端（windows的xshell或者mac自带的终端）

## 开始搭建
### (一）连接上VPS
我这里使用的是windows下的Xshell，下载地址：[点击下载Xshell](https://share.weiyun.com/5Jlnvnx)

下载完成后根据下图设置：

![image.png](https://www.hellojava.club/upload/2019/9/image-d13704db0c38497fb022d790f41ef620.png)

接着设置连接VPS账户名和密码，见下图：
![image.png](https://www.hellojava.club/upload/2019/9/image-9a8daef0e7b2457dab1e8a436eb76636.png)

出现下面这个图显示的画面才是连接成功，切记切记！
![image.png](https://www.hellojava.club/upload/2019/9/image-c2b248a3b4794af288b0fd84f3ca4b21.png)

### (二) 一键搭建
复制下面的代码，到xshell中右键选择粘贴，接着回车：
```shell
wget --no-check-certificate -O shadowsocks.sh https://www.hellojava.club/upload/2019/9/shadowsocks-61424f882f6746e8a7235b91ce8403b6.sh
chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log
```

然后如下图：
![image.png](https://www.hellojava.club/upload/2019/9/image-7216e8f2584f4ecf9f2eab946c2669f3.png)


接下来设置参数，如下图：
![image](https://www.hellojava.club/upload/2019/9/image-b50ba33847ed46e49df762ea0a1e720f.png)

然后balalal冒出来一堆英文字母，瀑布式的下滑，是不是有当黑客的感觉~

如果出现了下图显示的样子，恭喜，搭建成功：
![image](https://www.hellojava.club/upload/2019/9/image-a01f1efa3c2e4f9cbb8769ad9e81cb75.png)

记下来这个配置，我们需要在电脑或在手机上配置，然后连接上刚才搭建的SS服务。

## 连接

### （一）
下载客户端
1. [Windows客户端下载](https://share.weiyun.com/58iM1wR)
2. [安卓端客户端下载](https://share.weiyun.com/5g2Qbaq)
3. [Mac端下载](https://share.weiyun.com/5g2Qbaq)
4. IOS需要到APP Store去找了（等我的iPhone11到了找找看，哈哈）

下面演示windows客户端的配置方法吧，其它都类似，如下图：
![image.png](https://www.hellojava.club/upload/2019/9/image-34b34be6a5cb4cd28bf010e03e6888c0.png)

填好后点确定，然后右键小飞机，选择启动系统代理，如下图：
![image.png](https://www.hellojava.club/upload/2019/9/image-e07c80af8aa040e490d9259de8f1748c.png)

然后小飞机就亮起来了，下面可以试试能不能上谷歌查资料了。
![image.png](https://www.hellojava.club/upload/2019/9/image-f3641e9e5b1d446795df30d60643d53b.png)

香吗？香！

## 加速
利用BBR加速，原理是选择网络不拥塞的节点进行网络通讯，有兴趣的同学可以到github上看看：[直达链接](https://github.com/google/bbr)

首先复制下面的代码，粘贴在已经连接上vps的xshell上：
```shell
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh
```

回车，见下图：
![image](https://www.hellojava.club/upload/2019/9/image-3df9a1cca41e4ac5ba02efa41697ec0b.png)

接着按任意键开始，到下图的步骤时停顿时间会稍长点，莫慌：

![image](https://www.hellojava.club/upload/2019/9/image-5575b35730e04b968eb6dcf0deb8036f.png)

接着会问你是否要重启，输入y，回车，如下图：
![image.png](https://www.hellojava.club/upload/2019/9/image-4adc10ba74434b30abd7fbd80024962e.png)

然后尝试下快速冲浪的感觉吧~



PS：
有任何疑问可以在下方评论，或者加入网站底部的qq群~