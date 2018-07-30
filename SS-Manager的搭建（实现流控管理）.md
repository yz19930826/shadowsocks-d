1. 更新时间：2018年7月14日23:55:14-解决关掉SSH终端程序不运行的bug
[toc]
## 1. SS流控搭建
### 1.1 效果展示

![](http://p1hy9syru.bkt.clouddn.com/FhhCYDs-lX19v5NSK_yT1gTGyBaz)

![](http://p1hy9syru.bkt.clouddn.com/FlkpjwEmmpyKvZpb17sNgzqi1kyn)
### 1.2 前提步骤
#### 1.2.0 有VPS
买VPS的话我就不一步步的教了，之前的教程有，买了之后下面的就无需看了，直接来这边，参考教程：[Vultr搭建SS](http://www.hellojava.club/article/27)
#### 1.2.1 一枚邮箱
QQ邮箱就行，用来发送注册账号和充值密码的验证码。

## 2. 搭建开始
首先记住一条规则：Linux执行命令没有任何报错就证明是正确的。
### 2.1 安装Node.js
Q：Node.js是做什么用的？
A：是程序的运行环境，就如exe需要运行在window环境下一样。 
```
wget https://npm.taobao.org/mirrors/node/v8.9.3/node-v8.9.3-linux-x64.tar.xz
```
下载如下图:
![](http://p1hy9syru.bkt.clouddn.com/FhbytOb9-qXWIh_KnmO28I8DZsDv)
### 2.2 解压Node.js
下载下来的是一个压缩包，因此需要解压,如下：
```
xz -d node-v8.9.3-linux-x64.tar.xz
tar -xvf node-v8.9.3-linux-x64.tar
```
![](http://p1hy9syru.bkt.clouddn.com/FuQS_ACsmWyCFsiNWBKXIvk_CNaS)
### 2.3 建立软链接
Q:什么是软链接?
A:类似于Windows的快捷方式，可以快速的使用命令
下载的压缩包解压后相当于Windows中的绿色版，所以建立软链接后我们可以随地使用node的命令，具体如下：
```
ln -s -b /root/node-v8.9.3-linux-x64/bin/node /usr/local/bin/node
ln -s -b /root/node-v8.9.3-linux-x64/bin/npm /usr/local/bin/npm
node -v
```
结果如下图：
![](http://p1hy9syru.bkt.clouddn.com/Fs24aELWAWWMslmGy9BBXdOx3eWH)
出现v8.9.3说明Node安装成功

### 2.4 安装ss-manager
ss-manager是ss的管理程序,而上面安装的Node是ss-manager的运行环境。

执行：
```
npm i -g shadowsocks-manager --unsafe-perm 
```
执行结果如图：
![](http://p1hy9syru.bkt.clouddn.com/FobYCOWkJgE86bMD-bgLVpgQTVS3)

### 2.5 启动SS
这一步是启动ss程序，并指定和ss-manager监听的端口
```
ssserver -m aes-256-cfb -p 12345 -k abcedf --manager-address 127.0.0.1:6001 -d start
```
![](http://p1hy9syru.bkt.clouddn.com/FhDoBnQucxzDFvSFeIqBOVefAXQO)
### 2.6 执行ss-manager
#### 2.6.1 创建ssmgr的软链接
```
ln -s -b /root/node-v8.9.3-linux-x64/bin/ssmgr /usr/local/bin/ssmgr
```
#### 2.6.2 创建配置文件
```
vi /etc/ss.yml
```
接着点键盘i键，进入编辑模式，如下图：
![](http://p1hy9syru.bkt.clouddn.com/FqID7JzcQ_4SUtc3KfTPD9oLeLMx)

复制下面的内容,shift+insert粘贴：
```
type: s
shadowsocks:
  address: 127.0.0.1:6001
  # 这里的地址和端口需要跟上一步的 --manager-address 参数保持一致，连接上述 udp 端口
manager:
  address: 0.0.0.0:4001
  # 这个 address 参数会让程序监听一个 tcp 端口，用于接收 webgui 发送过来的控制命令
  password: '123456'
db: 'ss.sqlite'
```
接着按ESC按键，输入:wq退出（需在英文输入法下）

然后启动ss-manager:
```
screen -dmS ssmgr ssmgr -c /etc/ss.yml 
touch /usr/local/ssmgr.log
nohup ssmgr -c /etc/ss.yml > /usr/local/ssmgr.log 2>&1 &
```

### 2.7 安装流控
创建webgui.yml文件
```
vi /etc/webgui.yml
```
先根据自己的情况修改好下面的配置，然后复制，塞到webgui.yml文件中，最后:wq保存退出
```
type: m

# 这块不用动
manager:
  address: 0.0.0.0:4001
  password: '123456'

plugins:
  flowSaver:
    use: true
  user:
    use: true
  account:
    use: true
  #macAccount:
  #  use: true
  group:
    use: true
  #下面配置的是邮箱，用于用户注册和重置密码，这块根据自己的情况填写
  email:
    use: true
    username: 'charmtechnology@foxmail.com'
    password: 'xxxxxxxxxxx'
    host: 'smtp.qq.com'
  #下面配置的是流控网站
  webgui:
    use: true
    #host 默认就行
    host: '0.0.0.0'
    #端口 默认就好，如果有占用，则需要停用以前的占用
    port: '80'
    #域名 有需要绑定自己域名的填写
    site: 'http://ssmgr.hellojava.com'
    # cdn: 'http://xxx.xxx.com'
    # icon: 'icon.png'
    # skin: 'default'
    # googleAnalytics: 'UA-xxxxxxxx-x'
    gcmSenderId: '456102641793'
    gcmAPIKey: 'AAAAGzzdqrE:XXXXXXXXXXXXXX'
  # 下面是支付宝的配置
  # alipay:
  #   use: true
  #   appid: 2015012104922471
  #   notifyUrl: 'http://yourwebsite.com/api/user/alipay/callback'
  #   merchantPrivateKey: 'xxxxxxxxxxxx'
  #   alipayPublicKey: 'xxxxxxxxxxx'
  #   gatewayUrl: 'https://openapi.alipay.com/gateway.do'
  # webgui_telegram:
  #   use: true
  #   token: '191374681:AAw6oaVPR4nnY7T4CtW78QX-Xy2Q5WD3wmZ'
  # 下面这块是PayPal的配置
  # paypal:
  #   use: true
  #   mode: 'live' # sandbox or live
  #   client_id: 'At9xcGd1t5L6OrICKNnp2g9'
  #   client_secret: 'EP40s6pQAZmqp_G_nrU9kKY4XaZph'

db: 'webgui.sqlite'
```
接着执行流控程序：
```
screen -dmS weggui ssmgr -c /etc/webgui.yml
```

关闭防火墙：
```
systemctl stop firewalld.service

```
最后在浏览器访问你的vps ip来尝试一下吧~

### 结语
有疑问可以关注我的微信公众号(hellojava_club)咨询,或者扫描下方二维码关注。因为需要注意的细节很多，如果普遍反映搭建难度大的话，后面我会提供一键搭建脚本。