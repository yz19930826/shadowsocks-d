## Vultr VPS搭建SS教程


### 更新时间：

#### 2018年11月8日

加入视频教程

https://v.qq.com/txp/iframe/player.html?vid=b0787m86b90


#### 2018年8月5日(已结束)

Vultr做活动，新用户充5$送25$，如果你不是新用户，也有褥羊毛的机会：详情请戳：[Vultr充5送25美元的优惠活动进行中！](https://www.vultr.com/?ref=7772826-4F)

#### 2018年7月2日：

目前Vultr2.5 美元一个月的机器IP只有IPv6，而我们大部分的网络是IPv4，IPv4和IPv6之间没法互通网络，所以建议选择5美元的IPv4服务器。

#### 原文链接: 

原站内容更多（建议访问）
[哈喽爪哇](http://www.hellojava.club/article/27)


### 免费技术支持 

关注微信公众号

<img class="alignnone size-full wp-image-168" src="https://www.hellojava.club/wp-content/uploads/2018/08/FvSZtJik4tztuyfD95cZ6lQFoSQL.jpg" width="300" height="300" alt="" />

  不多说，先看目录，有自己需要的内容再往下面看，免得耽误大家宝贵的时间。
 

### 1.国外服务器的购买

这里我选择的是Vultr，对比了很多国外的服务器，这个蛮靠谱的，且搭建成功后看youtube720p完全无压力。

这里是链接：<a href="https://www.vultr.com/?ref=7772826-4F">Vultr The Infrastructure Cloud™</a>

当然，已经有服务器的小伙伴，直接从==快速搭建ShadowSocks==开始看

<h4>1.1 Vultr服务器价格</h4>

Vultr服务器按小时计费,最低0.004美元/h,算起来2.5美元/月，且destory掉服务器是不收费的，所以不用担心如果暂时没有使用还一直扣费的问题，如下图所示：

<img class="alignnone size-full wp-image-169" src="https://www.hellojava.club/wp-content/uploads/2018/08/34646066.jpg" width="1203" height="811" alt="image" />
<img class="alignnone size-full wp-image-170" src="https://www.hellojava.club/wp-content/uploads/2018/08/3735251.jpg" width="1169" height="803" alt="image" />
最低价格的服务器是512M的内存，500G的带宽，只能说99%的情况下完全够用了！

<h4>1.2 注册Vultr</h4>

首先打开<a href="https://www.vultr.com/?ref=7772826-4F">Vultr链接</a>，点击Create Account，如下图

<img class="alignnone size-full wp-image-171" src="https://www.hellojava.club/wp-content/uploads/2018/08/3883542-a393d98c540c2923-1.jpg" width="1240" height="775" alt="image" />

因为Vultr的网站是全英文的，对注册还是有要求的，当输入密码的时候，会显示出规范，如下图所示：

<img class="alignnone size-full wp-image-172" src="https://www.hellojava.club/wp-content/uploads/2018/08/35320802-1.jpg" width="534" height="673" alt="" />

<h4>1.3 充值Vultr</h4>

注册完成之后就是充值，Vultr提供4种充值方式，如下图：

<img class="alignnone size-full wp-image-173" src="https://www.hellojava.club/wp-content/uploads/2018/08/89036828.jpg" width="1280" height="483" alt="image" />

这里我选择支付宝，因为方便快捷，但是最低消费10美元，也不多，60多人民币，如下图：

<img class="alignnone size-full wp-image-174" src="https://www.hellojava.club/wp-content/uploads/2018/08/15151635.jpg" width="1049" height="735" alt="image" />
付款之后，就可以看到账户的钱多了

<h4>1.4 选择VPS的位置</h4>

首先，位置很重要！我们如何选择呢，当然有科学的办法，ping它！

Vultr的服务器有很多位置，下面我测试的东京节点和新加坡节点的数据如下：
<img class="alignnone size-full wp-image-175" src="https://www.hellojava.club/wp-content/uploads/2018/08/24848076.jpg" width="776" height="257" alt="image" />

<hr />

<img class="alignnone size-full wp-image-176" src="https://www.hellojava.club/wp-content/uploads/2018/08/6285681.jpg" width="735" height="255" alt="image" />

这么看来还是东京的节点速度比较好，当然这个因人而异，在中国不同的地理位置访问国外不同位置的服务器速度也不一样。（下面提供了下载地址,Windows操作系统下载下来双击运行即可）。

测速脚本下载地址：
<a href="https://www.hellojava.club/wp-content/uploads/2019/01/测速.txt">点我下载 测速.txt 注意将后缀改成bat后双击执行</a>

脚本内容如下：

<pre><code class="">@echo off
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
</code></pre>

根据测速的结果，我选择东京位置的VPS

<h4>1.5 创建VPS</h4>

左侧菜单栏Servers，点击+，如下图：

<img class="alignnone size-full wp-image-177" src="https://www.hellojava.club/wp-content/uploads/2018/08/47817578.jpg" width="1280" height="407" alt="" />

选择VPS的位置，如下图：

<img class="alignnone size-full wp-image-178" src="https://www.hellojava.club/wp-content/uploads/2018/08/80347886.jpg" width="1276" height="593" alt="" />

选择操作系统和价格，如下图：

<img class="alignnone size-full wp-image-179" src="https://www.hellojava.club/wp-content/uploads/2018/08/57275913.jpg" width="1280" height="787" alt="" />

点击最下面的Deploy Now，如下图：

<img class="alignnone size-full wp-image-180" src="https://www.hellojava.club/wp-content/uploads/2018/08/72614747.jpg" width="1169" height="94" alt="" />

创建成功
<img class="alignnone size-full wp-image-181" src="https://www.hellojava.club/wp-content/uploads/2018/08/96724049.jpg" width="1280" height="532" alt="" />

<h4>1.6 VPS的信息</h4>

安装成功之后，点击Manage
<img class="alignnone size-full wp-image-182" src="https://www.hellojava.club/wp-content/uploads/2018/08/5303346.jpg" width="1260" height="129" alt="" />

可以看到你购买的VPS的信息，如下图所示：

<img class="alignnone size-full wp-image-183" src="https://www.hellojava.club/wp-content/uploads/2018/08/60924560.jpg" width="1273" height="383" alt="" />

ping一下ip地址，100ms多一点，这个速度相当可以了，如下图：

<img class="alignnone size-full wp-image-184" src="https://www.hellojava.club/wp-content/uploads/2018/08/85210345.jpg" width="727" height="204" alt="" />

<h3>2. VPS的使用</h3>

<h4>2.1 下载Shell</h4>

当然是选择先连接它了，我们选择的工具是XShell

下载地址：<a href="https://share.weiyun.com/5Jlnvnx">Xshell下载</a>（已更新到Xshell6永久破解版 2019年4月14日）

下载完成之后安装，下一步即可

<img class="alignnone size-full wp-image-185" src="https://www.hellojava.club/wp-content/uploads/2018/08/93916574.jpg" width="624" height="442" alt="" />

接着选择免费为家庭/学校

<img class="alignnone size-full wp-image-186" src="https://www.hellojava.club/wp-content/uploads/2018/08/78823393.jpg" width="624" height="442" alt="" />

语言选择中文：

<img class="alignnone size-full wp-image-187" src="https://www.hellojava.club/wp-content/uploads/2018/08/31720650.jpg" width="624" height="476" alt="" />

安装成功后打开

<h4>2.2 连接VPS</h4>

打开Xshell，选择文件->新建，输入VPS的IP，IP地址就在Vultr的管理页面上，如下图所示：

<img class="alignnone size-full wp-image-188" src="https://www.hellojava.club/wp-content/uploads/2018/08/5952980.jpg" width="667" height="613" alt="" />

点击确定，输入用户名，默认应该为root，如下图：

<img class="alignnone size-full wp-image-189" src="https://www.hellojava.club/wp-content/uploads/2018/08/42093165.jpg" width="398" height="239" alt="" />

接着输入密码：

<img class="alignnone size-full wp-image-190" src="https://www.hellojava.club/wp-content/uploads/2018/08/60518802.jpg" width="504" height="485" alt="" />

连接成功：
<img class="alignnone size-full wp-image-191" src="https://www.hellojava.club/wp-content/uploads/2018/08/22145504.jpg" width="881" height="324" alt="" />

<h3>3. 快速搭建ShadowSocks(二选一)</h3>

<h4>3.1 一键安装</h4>

<h5>3.1.1 使用方法</h5>

在Xshell中依次运行以下命令

<pre><code class="">wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh

chmod +x shadowsocks.sh
./shadowsocks.sh 2&gt;&amp;1 | tee shadowsocks.log
</code></pre>

接着按照提醒输入你的密码，端口和加密方式，如下图：

<img class="alignnone size-full wp-image-192" src="https://www.hellojava.club/wp-content/uploads/2018/08/98045672.jpg" width="902" height="492" alt="" />
<img class="alignnone size-full wp-image-193" src="https://www.hellojava.club/wp-content/uploads/2018/08/25013694.jpg" width="874" height="346" alt="" />

然后可以去听首歌~，成功安装之后有你配置的信息显示，记住这些信息，然后跳过下面的手动安装部分，直接去看客户端连接部分即可，如下图：


<img class="alignnone size-full wp-image-194" src="https://www.hellojava.club/wp-content/uploads/2018/08/14336343.jpg" width="568" height="218" alt="" />

<blockquote>
  以上脚本来源于秋水逸冰
</blockquote>

<strong>注意：如果使用上面的一键安装，手动安装的部分就可跳过了，直接看下面的连接。</strong>

<h4>3.2 手动安装</h4>

<h5>3.2.1 安装依赖包</h5>

在XShell的控制台输入：

<pre><code class="">curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"
python get-pip.py
</code></pre>

一个个的来，如下图：

<img class="alignnone size-full wp-image-195" src="https://www.hellojava.club/wp-content/uploads/2018/08/44431815.jpg" width="833" height="358" alt="" />

<h5>3.2.2 安装ShadowSocks</h5>

<pre><code class="">pip install --upgrade pip
pip install shadowsocks
</code></pre>

如下图：

<img class="alignnone size-full wp-image-196" src="https://www.hellojava.club/wp-content/uploads/2018/08/8720751.jpg" width="834" height="299" alt="" />

<h5>3.2.3 创建ShadowSocks配置文件</h5>

<h6>3.2.3.1 单用户</h6>

<pre><code class="">vi /etc/shadowsocks.json
</code></pre>

输入以下内容，然后点ESC后输入:wq保存退出

<pre><code class="">{
  "server": "0.0.0.0",
  "server_port": 2018,
  "password": "12345678",
  "method": "aes-256-cfb"
}

</code></pre>

<h6>3.2.3.2 多用户</h6>

（可选，配置了单用户就不要配置这个，多用户的意思是可以用不同的端口和密码来登录，单用户的也可以多个人一起上网，只是用的是一套端口和密码）多用户的配置文件如下：

<pre><code class="">{
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
</code></pre>

我采取的是单用户配置，如下图所示：

<img class="alignnone size-full wp-image-197" src="https://www.hellojava.club/wp-content/uploads/2018/08/15345954.jpg" width="710" height="203" alt="" />
<img class="alignnone size-full wp-image-198" src="https://www.hellojava.club/wp-content/uploads/2018/08/88691281.jpg" width="811" height="487" alt="" />

<h5>3.2.4 配置防火墙</h5>

<pre><code class="">systemctl stop firewalld.service
</code></pre>

<img src="http://p1hy9syru.bkt.clouddn.com/17-12-30/27165290.jpg" alt="" />

<h5>3.2.5 启动ShadowSocks服务</h5>

<pre><code class="">ssserver -c /etc/shadowsocks.json -d start

</code></pre>

下面的是关闭，启动成功之后不要执行

<h5>3.2.6 关闭ShadowSocks服务</h5>

<pre><code class="">ssserver -c /etc/shadowsocks.json -d stop 
</code></pre>

如图所示：
<img class="alignnone size-full wp-image-199" src="https://www.hellojava.club/wp-content/uploads/2018/08/34335669.jpg" width="650" height="117" alt="" />

<h3>4. 连接ShadowSocks，体会科学上网的魅力</h3>

<h4>4.1 Windows客户端</h4>

下载地址：
<a href="https://share.weiyun.com/58iM1wR">Shadowsocks-4.0.7.zip</a>

下载完成之后解压打开，如下图所示：

<img class="alignnone size-full wp-image-200" src="https://www.hellojava.club/wp-content/uploads/2018/08/45931732.jpg" width="578" height="567" alt="" />

按照你自己的配置完成之后，点击确定，然后在托盘中右键这个小飞机，启动系统代理
，灰色的小飞机就会亮起来，如下图：

<img class="alignnone size-full wp-image-201" src="https://www.hellojava.club/wp-content/uploads/2018/08/90649607.jpg" width="324" height="83" alt="" />

然后就可以畅游网络了~

测试地址：
- <a href="https://www.google.com.hk/">谷歌</a>
- <a href="https://www.youtube.com/">Youtube</a>
- <a href="https://twitter.com/?lang=zh-cn">推特</a>

<h4>4.2 安卓连接</h4>

下载地址：<a href="https://share.weiyun.com/5g2Qbaq">shadowsocks.apk</a>

配置和windows差不多，配置完成后点击右上角的开启按钮即可，如下图：

<img class="alignnone size-full wp-image-202" src="https://www.hellojava.club/wp-content/uploads/2018/08/2617202.jpg" width="473" height="820" alt="" />

<h4>4.3 IOS连接</h4>

参考链接：<a href="http://www.360doc.com/content/17/0614/06/37032448_662846097.shtml">http://www.360doc.com/content/17/0614/06/37032448_662846097.shtml</a>

<h4>4.4 MAC 连接</h4>

下载地址：
<a href="https://share.weiyun.com/5mbuAmM">ShadowsocksX-2.6.3.dmg</a>

<h3>5. 测试结果</h3>

4K Youtube完成无压力
<img class="alignnone size-full wp-image-203" src="https://www.hellojava.club/wp-content/uploads/2018/08/28663474.jpg" width="1280" height="497" alt="image" />

<h3>6. 写在后面的话</h3>

水平有限，希望大家看到错误可以指出，我会及时更正。

还有，会面我会推出可视化搭建界面，更简单，更快捷，关注本站吧~