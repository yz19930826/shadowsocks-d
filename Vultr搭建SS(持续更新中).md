## Vultr VPS搭建SS教程

### 更新时间：

2018年8月5日

Vultr做活动，新用户充5$送25$，如果你不是新用户，也有褥羊毛的机会：详情请戳：[Vultr充5送25美元的优惠活动进行中!](https://www.hellojava.club/article/213)

2018年7月2日：

目前Vultr2.5 美元一个月的机器IP只有IPv6，而我们大部分的网络是IPv4，IPv4和IPv6之间没法互通网络，所以建议选择5美元的IPv4服务器。

### 原站链接:
[哈喽爪哇-让技术更有传播的价值 http://www.hellojava.club](https://www.hellojava.club/)

### 免费技术支持

关注微信公众号

![](http://p1hy9syru.bkt.clouddn.com/FvSZtJik4tztuyfD95cZ6lQFoSQL)


> 不多说，先看目录，有自己需要的内容再往下面看，免得耽误大家宝贵的时间。
[toc]

### 1.国外服务器的购买

这里我选择的是Vultr，对比了很多国外的服务器，这个蛮靠谱的，且搭建成功后看youtube720p完全无压力。

这里是链接：[Vultr The Infrastructure Cloud™](https://www.vultr.com/?ref=7295935)


当然，已经有服务器的小伙伴，直接从==快速搭建ShadowSocks==开始看

#### 1.1 Vultr服务器价格
Vultr服务器按小时计费,最低0.004美元/h,算起来2.5美元/月，且destory掉服务器是不收费的，所以不用担心如果暂时没有使用还一直扣费的问题，如下图所示：
![image](http://p1hy9syru.bkt.clouddn.com/17-12-29/34646066.jpg)
![image](http://p1hy9syru.bkt.clouddn.com/17-12-29/3735251.jpg)
最低价格的服务器是512M的内存，500G的带宽，只能说99%的情况下完全够用了！
#### 1.2 注册Vultr
首先打开[Vultr链接](https://www.vultr.com/?ref=7295935)，点击Create Account，如下图

![image](http://upload-images.jianshu.io/upload_images/3883542-a393d98c540c2923.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

因为Vultr的网站是全英文的，对注册还是有要求的，当输入密码的时候，会显示出规范，如下图所示：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/35320802.jpg)

#### 1.3 充值Vultr
注册完成之后就是充值，Vultr提供4种充值方式，如下图：
![image](http://p1hy9syru.bkt.clouddn.com/17-12-29/89036828.jpg)

这里我选择支付宝，因为方便快捷，但是最低消费10美元，也不多，60多人民币，如下图：
![image](http://p1hy9syru.bkt.clouddn.com/17-12-29/15151635.jpg)
付款之后，就可以看到账户的钱多了

#### 1.4 选择VPS的位置
首先，位置很重要！我们如何选择呢，当然有科学的办法，ping它！

Vultr的服务器有很多位置，下面我测试的东京节点和新加坡节点的数据如下：
![image](http://p1hy9syru.bkt.clouddn.com/17-12-29/24848076.jpg)

---
![image](http://p1hy9syru.bkt.clouddn.com/17-12-29/6285681.jpg)

这么看来还是东京的节点速度比较好，当然这个因人而异，在中国不同的地理位置访问国外不同位置的服务器速度也不一样。（下面提供了下载地址,Windows操作系统下载下来双击运行即可）。

测速脚本下载地址：
[点我下载 测速.bat](http://p1hy9syru.bkt.clouddn.com/%E6%B5%8B%E9%80%9F.bat)

脚本内容如下：

```
@echo off
echo ===========================================
echo 东京
ping hnd-jp-ping.vultr.com

echo ============================================
echo 新加坡
ping sgp-ping.vultr.com

echo ===========================================
echo (AU) Sydney, Australia[悉尼]
ping syd-au-ping.vultr.com

echo ===========================================
echo 德国 法兰克福
ping fra-de-ping.vultr.com

echo ===========================================
echo 荷兰 阿姆斯特丹
ping ams-nl-ping.vultr.com

echo ===========================================
echo 英国 伦敦
ping lon-gb-ping.vultr.com

echo ===========================================
echo 法国 巴黎
ping par-fr-ping.vultr.com

echo ===========================================
echo 美东 华盛顿州 西雅图
ping wa-us-ping.vultr.com

echo ===========================================
echo 美西 加州 硅谷
ping sjo-ca-us-ping.vultr.com

echo ===========================================
echo 美西 加州 洛杉矶
ping lax-ca-us-ping.vultr.com

echo ===========================================
echo 美东 芝加哥
Chicago, Illinois[美东 芝加哥]
ping il-us-ping.vultr.com

echo ===========================================
echo 美中 德克萨斯州 达拉斯
ping tx-us-ping.vultr.com

echo ===========================================
echo 美东 新泽西
ping nj-us-ping.vultr.com

echo ===========================================
echo 美东 乔治亚州 亚特兰大
ping ga-us-ping.vultr.com

echo ===========================================
echo 美东 佛罗里达州 迈阿密
ping fl-us-ping.vultr.com	
pause
```
根据测速的结果，我选择东京位置的VPS

#### 1.5 创建VPS
左侧菜单栏Servers，点击+，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/47817578.jpg)

选择VPS的位置，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/80347886.jpg)

选择操作系统和价格，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/57275913.jpg)

点击最下面的Deploy Now，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/72614747.jpg)

创建成功
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/96724049.jpg)

#### 1.6 VPS的信息
安装成功之后，点击Manage
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/5303346.jpg)

可以看到你购买的VPS的信息，如下图所示：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/60924560.jpg)

ping一下ip地址，100ms多一点，这个速度相当可以了，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/85210345.jpg)

### 2. VPS的使用

#### 2.1 下载Shell
当然是选择先连接它了，我们选择的工具是XShell

下载地址：[Xshell下载](http://p1hy9syru.bkt.clouddn.com/Xshell6.exe)（已更新到Xshell6）

下载完成之后安装，下一步即可

![](http://p1hy9syru.bkt.clouddn.com/17-12-30/93916574.jpg)

接着选择免费为家庭/学校

![](http://p1hy9syru.bkt.clouddn.com/17-12-30/78823393.jpg)

语言选择中文：

![](http://p1hy9syru.bkt.clouddn.com/17-12-30/31720650.jpg)

安装成功后打开

#### 2.2 连接VPS
打开Xshell，选择文件->新建，输入VPS的IP，IP地址就在Vultr的管理页面上，如下图所示：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/5952980.jpg)

点击确定，输入用户名，默认应该为root，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/42093165.jpg)

接着输入密码：

![](http://p1hy9syru.bkt.clouddn.com/17-12-30/60518802.jpg)

连接成功：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/22145504.jpg)

### 3. 快速搭建ShadowSocks(二选一)

#### 3.1 一键安装
##### 3.1.1 使用方法

在Xshell中依次运行以下命令

```
wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh

chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log
```
接着按照提醒输入你的密码，端口和加密方式，如下图：

![](http://p1hy9syru.bkt.clouddn.com/17-12-31/98045672.jpg)
![](http://p1hy9syru.bkt.clouddn.com/17-12-31/25013694.jpg)

然后可以去听首歌~，成功安装之后有你配置的信息显示，记住这些信息，然后跳过下面的手动安装部分，直接去看客户端连接部分即可，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-31/14336343.jpg)

> 以上脚本来源于秋水逸冰

**注意：如果使用上面的一键安装，手动安装的部分就可跳过了，直接看下面的连接。**
#### 3.2 手动安装

##### 3.2.1 安装依赖包
在XShell的控制台输入：

```
curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"
python get-pip.py
```
一个个的来，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/44431815.jpg)

##### 3.2.2 安装ShadowSocks

```
pip install --upgrade pip
pip install shadowsocks
```
如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/8720751.jpg)

##### 3.2.3 创建ShadowSocks配置文件

###### 3.2.3.1 单用户
```
vi /etc/shadowsocks.json
```
输入以下内容，然后点ESC后输入:wq保存退出

```
{
  "server": "0.0.0.0",
  "server_port": 2018,
  "password": "12345678",
  "method": "aes-256-cfb"
}

```
###### 3.2.3.2 多用户
（可选，配置了单用户就不要配置这个，多用户的意思是可以用不同的端口和密码来登录，单用户的也可以多个人一起上网，只是用的是一套端口和密码）多用户的配置文件如下：

```
{
    "server": "0.0.0.0",
    "port_password": {
        "8381": "password1",
        "8382": "password2",
        "8383": "password3",
        "8384": "password4"
    },
    "timeout": 300,
    "method": "aes-256-cfb"
}
```


我采取的是单用户配置，如下图所示：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/15345954.jpg)
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/88691281.jpg)

##### 3.2.4 配置防火墙

```
systemctl stop firewalld.service
```
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/27165290.jpg)

##### 3.2.5 启动ShadowSocks服务


```
ssserver -c /etc/shadowsocks.json -d start

```
下面的是关闭，启动成功之后不要执行
##### 3.2.6 关闭ShadowSocks服务
```
ssserver -c /etc/shadowsocks.json -d stop 
```
如图所示：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/34335669.jpg)


### 4. 连接ShadowSocks，体会科学上网的魅力

#### 4.1 Windows客户端
下载地址：
[Shadowsocks-4.0.7.zip](http://p1hy9syru.bkt.clouddn.com/Shadowsocks-4.0.7.zip)

下载完成之后解压打开，如下图所示：
![](http://p1hy9syru.bkt.clouddn.com/18-1-18/45931732.jpg)

按照你自己的配置完成之后，点击确定，然后在托盘中右键这个小飞机，启动系统代理
，灰色的小飞机就会亮起来，如下图：
![](http://p1hy9syru.bkt.clouddn.com/17-12-30/90649607.jpg)

然后就可以畅游网络了~

测试地址：
- [谷歌](https://www.google.com.hk/)
- [Youtube](https://www.youtube.com/)
- [推特](https://twitter.com/?lang=zh-cn)


#### 4.2 安卓连接
下载地址：[shadowsocks.apk](http://p1hy9syru.bkt.clouddn.com/shadowsocks.apk)

配置和windows差不多，配置完成后点击右上角的开启按钮即可，如下图：

![](http://p1hy9syru.bkt.clouddn.com/17-12-30/2617202.jpg)

#### 4.3 IOS连接

参考链接：[http://www.360doc.com/content/17/0614/06/37032448_662846097.shtml](http://www.360doc.com/content/17/0614/06/37032448_662846097.shtml)

#### 4.4 MAC 连接
下载地址：
[ShadowsocksX-2.6.3.dmg](http://p1hy9syru.bkt.clouddn.com/ShadowsocksX-2.6.3.dmg)

### 5. 测试结果
4K Youtube完成无压力
![image](http://p1hy9syru.bkt.clouddn.com/17-12-30/28663474.jpg)


### 6. 写在后面的话
水平有限，希望大家看到错误可以指出，我会及时更正。

还有，会面我会推出可视化搭建界面，更简单，更快捷，关注本站吧~

