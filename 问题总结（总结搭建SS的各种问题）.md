## 此文档记录搭建SS的各种问题
### 希望小伙伴们积极提出自己的问题
### 目前发现的记录如下：

## Xshell总是连接不上？
首先ping一下ip地址，观察是否有数据返回，如我的IP地址为：45.77.29.91。
```win+r```调出运行,输入cmd，如下图：

![](http://p1hy9syru.bkt.clouddn.com/18-2-5/2750126.jpg)

点击确定后，会出现一个黑框，输入ping 45.77.29.91,如下图：

![](http://p1hy9syru.bkt.clouddn.com/18-2-5/34377431.jpg)

如果可以收到IP的回复，则说明你的vps正常。如果显示请求超时，如下图，则说明该vps ip不能使用，请销毁重建，直到可以ip可以ping通为止(如果一个地区ip经常ping不通，建议换个地区重新创建)。

![](http://p1hy9syru.bkt.clouddn.com/18-2-5/75962613.jpg)


## Windows打开shadowsocks客户端，程序直接停止运行。

[戳我下载](https://download.microsoft.com/download/F/9/4/F942F07D-F26F-4F30-B4E3-EBD54FABA377/NDP462-KB3151800-x86-x64-AllOS-ENU.exe)，安装即可，这是微软的官方运行库，请放心。


## 如果上面的问题都不存在？
先确定你是否连过其它代理，如蓝灯，或者一些浏览器插件，如果连过请全部断开再试。如果没有用其它代理还是连接不上，则在xshell中执行下面的命令重启ss：
``` 
ssserver -c /etc/shadowsocks.json -d restart
```
好了，再尝试一下是否能科学上网了。
