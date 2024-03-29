# 一、概要
本文以大白话的角度讲解了VPS的概念、Vultr服务器的购买和使用，即使你没有太多的计算机基础，也可以轻松的看懂本文。

其内容包括:
1. 什么是VPS？
2. 为什么选择Vultr？
3. 如何选择Vultr的优惠以实现利益最大化？
3. Vultr VPS的注册、登录、购买教程
4. 如何选择Vultr VPS的服务器位置以实现高速网上冲浪？
5. 如何确定购买的Vultr VPS是可用的？
6. 如何优雅的连接Vultr VPS？
7. Vultr VPS的使用概要（包含但不限于如何搭建博客，网盘，实现自己的自由冲浪等等）

上述内容的每一步比较难以理解的点都以图文的方式来展示，让来看文章的你，知其然并知其所以然~

那么下面好戏开场

# 二、什么是VPS
在百度百科上，对VPS的描述是[虚拟专用服务器](https://baike.baidu.com/item/%E8%99%9A%E6%8B%9F%E4%B8%93%E7%94%A8%E6%9C%8D%E5%8A%A1%E5%99%A8/5613529)，这个名词相当的抽象，令人丈二的和尚摸不着头脑。

透过现象看本质，实际上我们可以理解VPS就是一个远程的电脑，和你家用玩LOL的电脑无异，你可以使用家用的电脑去操作这个远程的电脑让它做点有意思的事情。
![你懂得.png](https://img-blog.csdnimg.cn/img_convert/5775fa08ecdc79a86269d8707253e68c.png)

大家可能会问，既然都是电脑，我可以使用家里的电脑来代替VPS吗？省下来的的钱买点猪肉吃不香吗？

理论上可行的，但是实际上有一些因素限制，甚至于让你吃不上猪肉还得倒贴些买牛肉的钱

比如：
1. VPS可以24小时的运行，而无需付电费，只需要使用费，也没有设备折损费（电费和折损费加起来，啧啧啧~）

2. VPS有公网IP地址，而我们大部分连的家用宽带是没有公网IP的。什么是公网IP地址？我们记住**任何概念基本都是现实世界的抽象**，**IP地址和邮政地址无异**，只有填写了正确的邮政地址，快递员才能找到你，你的快递包裹才能正确的收到。同理在计算机上，有个独立的公网IP地址，别人才能找到你~

3. 另外最重要的一点是，它可以做一些你的计算机无法做到的事情，比如访问Google，当然。你也可以肉身转移到国外去访问，这也是一个不错的思路，只是机票有点儿费钱。

# 三、为什么选择Vultr？
为什么在茫茫VPS厂商中选中了Vultr VPS呢，当然是Vultr比较优秀喽

从付费方式上来讲，**Vultr按小时付费 ，随用随开，不用即停**，没有其余费用，也就是说在我们在需要使用VPS的时候创建一个，不需要使用的时候直接销毁即可，也不会有额外的支出。

支付方式上，它支持支付宝付款，支付宝大家基本都有吧。。

支持免费快照功能，一次搭建，到处运行。如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/d164d48f72df630efe9c0b5973c934e3.png)

若VPS-1因为某些特殊的原因无法访问了，那么我们我可以把VPS-1当前运行的环境做一个快照恢复至VPS-2，这样VPS-2就完全复制了VPS-1的运行环境，而不需要把所有的数据啊软件啊都重新安装搭建一遍，相当方便。

支持换IP地址，而且是免费的，这个重要性就不言而喻了，因为某些原因导致此IP无法访问，那么我们可以重新换个IP，至于什么原因导致IP无法访问，你懂得
![image.png](https://img-blog.csdnimg.cn/img_convert/d0891bb3c7767d8c951b2c57eaf1584d.png)

无需备案，备案这个事情实属国内的特色，意思就是你购买的域名如果想指向这个VPS的IP，需要向有关部门说明下你拿来干啥的，而购买国外的VPS则不需要这个操作，而Vultr就是国外的VPS。

免费IPV6地址。之前说的IP地址都是IPV4的地址，Vultr同样支持IPV6地址，而且是免费的。那IPV4和IPV6到底是什么鬼，它们之间有什么关系？这东西概念一套一套的，忽略一些细节，我们只要知道IPV6地址比IPV4的更长就行了，目前IPV4的地址快不够用了，所以又搞了个升级版IPV6，其更大，更长，更...，别想歪了啊。

据说IPV6可以把地球上的每粒沙子都给个地址编码，实属牛批，万物互联首选，现在国家更在大力推行IPV6，我们的运营商网络很大一部分已经支持IPV6了，说了这么多，对我们的好处是什么？一句话，IPV4和IPV6是独立的，如果IPV4地址我们访问不了，可以试试IPV6访问，多个路，多个选择嘛。具体IPV6的使用方法我会在后文详细介绍

# 四、如何优惠的购买Vultr，以实现利益最大化？
Vultr对新用户是有优惠政策，经过调研，较优的方案有两种：

1. 充多少送多少的活动，最高送100美刀，送的美刀有效期是1年 [==>点此链接注册Vultr享受充值多少送多少的优惠](https://www.vultr.com/zh/match/?ref=7295935)

2. 充10送100美刀的活动，但是赠送的美刀有效期只有14天 [==>点此链接注册Vultr享受充10送100$的优惠](https://www.vultr.com/?ref=9180669-8H)

优惠摆在这儿了，如果想长期使用，可以选择第一种方案。如果想爽一把，直接上高配置机器，则可以选择第二种方案，大家按需选择。

# 五、Vultr的注册、登录与优惠确认
正戏开场，由于Vultr是国外的服务器厂商，网站也是全英文的，下面以图文的方式介绍Vultr的注册与登录

## 5.1 Vultr的注册
选择适合自己的优惠，点击后面的链接进入到网站

优惠一：[Vultr VPS充值多少送多少活动页面](https://www.vultr.com/zh/match/?ref=7295935)
优惠二：[Vultr VPS充值10送100活动页面](https://www.vultr.com/?ref=9180669-8H)

进入之后网站可能会验证访问者是不是人类，会让选择公交车或者轮船，正常选择就行，如果选择错了也没关系，会让你重新选择。

![确认自己是人类](https://img-blog.csdnimg.cn/img_convert/288bfcb0737d2134c9444ffa8222fb7e.png)

![证明自己是人类](https://img-blog.csdnimg.cn/img_convert/e4022a723be3cb9f592be2cfb13cd551.png)

验证通过之后会进入到Vultr网站的首页，如下图，直接输入邮箱和密码点击创建账户（Create Account）即可

![image.png](https://img-blog.csdnimg.cn/img_convert/c2f3e9b5bb101d8289e6d171fe5da7b0.png)

这里需要注意的是，密码的规则有四个，必须同时满足才算是一个有效的密码，即
```
1. 必须有一个大写字母
2. 必须有一个小写字母
3. 必须有一个数字
4. 不少于10个字符
```
## 5.2 Vultr服务器的登录
创建账户完成后会直接跳转到Billing标签页，即已经是登录状态。如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/29bf5f3beb93a2a74c97bb1d0002fb53.png)

如果没有登录的话，可以点击右边这个链接输入账号密码进行进行登录 👉🏻[点我进入Vultr登录页](https://my.vultr.com/?ref=7295935)

## 5.3 Vultr的优惠确认与充值

既然我们是通过优惠专享链接注册的，那么必然要确认下优惠是否已经下发，如下图，按照标记的步骤确认即可
![image.png](https://img-blog.csdnimg.cn/img_convert/78f632d35965533d484fb06a59ca394c.png)

接着会跳转到支付宝的付款页面上，扫码付款即可

付款成功后美元即到账
![美元到账图](https://img-blog.csdnimg.cn/img_convert/b7a352991c7d4563a60646317a6c9701.png)

## 5.4 邮箱验证
接下来需要验证下邮箱，点击```Click here to send a verfication e-mail```，如下图
![image.png](https://img-blog.csdnimg.cn/img_convert/8c0bfe4418afc38739052c9fad9c1469.png)

接着到邮箱里面，打开Vultr官方发来的链接，如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/eec1007c7dc67076824f62c5d5232b26.png)

打开链接后会直接跳转到Vultr官网，并显示验证成功，如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/f7049da93278326a9e4c2092a9869ffa.png)



# 六、Vultr的服务器的购买
充值完成和验证完成后即可选择适合自己的VPS机器了，点击```Products```-> ```+```号，如下图
![image.png](https://img-blog.csdnimg.cn/img_convert/792200b3e0dbd4e0c8c9d1b575beb156.png)


VPS主要分了四个类别，我在图中都有标记，大家按需选择，博主比较穷，选择【一般性能的VPS】就行，贫穷限制了我在网上自由冲浪的权利😭
![image.png](https://img-blog.csdnimg.cn/img_convert/ec26227462c39971eb65a62137ff27db.png)

**接着选择VPS的CPU和存储**，如下图，我依然贴心的介绍了一下，大家按需选择~
![image.png](https://img-blog.csdnimg.cn/img_convert/78b93aada9b6d576921def799a44d187.png)

接下来是选择VPS的位置，也就是你要买的VPS，它是来自遥远的阿姆斯特丹，还是纽约，完全取决于你的选择。大家可能选择恐惧症犯了，这么多位置，该选择哪个呢？这里博主当然会给大家一个标准，选择最适合自己的VPS

![Vultr VPS位置选择](https://img-blog.csdnimg.cn/img_convert/aed3a66ce1312898f1b12e52df3467e0.png)


那么先来聊聊，选择的标准是什么？这里有两个参数需要介绍下，那就是延迟和带宽

**什么是延迟？** 简单来说就是从我们的电脑访问到VPS一个来回所经历的时间，博主当然不会用这么抽象的话来表示延迟的含义，下面让周星星登场来解释下

想当年周星星对柏芝说出经典的一句台词：“我养你啊”，柏芝回复说：“你先养好自己吧，傻瓜”，延迟就是从周星星说出“我养你啊”，到耳朵听到“你先养好你自己吧，傻瓜”这句话所经历的时间，周星星期待尽快得到回复，因此延迟越小越好
![image.png](https://img-blog.csdnimg.cn/img_convert/757ecf924a57f85493062339f6209f4f.png)

又比如我们打英雄联盟游戏，右上角都会显示一个ping值，这个值越低，我们操作越顺滑，这个值越高，就越想砸键盘。

![](https://img-blog.csdnimg.cn/img_convert/837c15083f78c39afc2895ce3bb3a673.gif)

什么是带宽呢？即单位时间内通过的数据量，简单来说，在我们下载动作小视频的时候，都会显示一个下载的速度，这个速度就可以理解为带宽，很明显，这个值越大越好，在SpeedTest可以测试我们当前使用的宽带的网速，网址如下：[->https://www.speedtest.cn/](https://www.speedtest.cn/)

![网速测试](https://img-blog.csdnimg.cn/img_convert/a6bd42417c3c3ccd66677058e3a03704.png)

介绍完了延迟和带宽的概念，并且知道了要选择延迟小的和带宽大的VPS，下面就是验证不同位置的VPS的延迟和带宽的区别，这里Vultr给出了官方的测试地址：[→Vultr VPS不同位置延迟和带宽测评地址](https://www.vultr.com/zh/resources/faq/#downloadspeedtests)，点开如下图
![image.png](https://img-blog.csdnimg.cn/img_convert/50019d78c2e10bcb0f45699020d23dc7.png)


如上图，标出了**位置**、**测试延迟**和**测试带宽**的三个点，我们可以选择不同的位置进行延迟和带宽测试，对于**测试延迟**，可以在```CMD```窗口使用```ping```命令测试，即```ping mad-es-ping.vultr.com```，结果如下图：
![Vultr VPS延迟测试](https://img-blog.csdnimg.cn/img_convert/d01849c9672edf9d9f10ffd8c0f55b66.png)

对于带宽的测试，我们直接点击页面上的100M，会直接触发下载操作，观察下载的速度即可，如下图

![带宽测试](https://img-blog.csdnimg.cn/img_convert/77e96b2197af6e4674814fc6110ce67e.png)

经过一顿操作猛如虎的设计，博主我选到了最合适的位置，那就是新加坡！,延迟只有125ms左右，稳得一批

![image.png](https://img-blog.csdnimg.cn/img_convert/e32e86536702b966825d7034213023b7.png)


那么接下来继续部署咱们得VPS，选择新加坡位置，如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/5f42c12beba349869cac08bf4f202cb8.png)

**选择操作系统**，咱们选择```CentOS 8 Stream X64```，如下图：
![Vultr操作系统](https://img-blog.csdnimg.cn/img_convert/49e45ce21f5fdaf2719d958c822396a9.png)

**选择硬盘容量和CPU核数**等配置，明码标价，按需选择，按照博主的作风，那肯定选择了最具有性价比的（最便宜的，哈哈）

![配置图](https://img-blog.csdnimg.cn/img_convert/3d25b85e5053a9af6ba7ff9bbdca9492.png)


**自动备份选择** ，类似于手机的自动备份机制，可以自动备份VPS的数据，如遇到问题，可以快速恢复，这个也是按需选择
![image.png](https://img-blog.csdnimg.cn/img_convert/162a2e9a73e7f6b5d4ed8cda58bdbab6.png)

**其它VPS特性**选择，这里主要勾选的是IPV6，后续有用，主要还是免费的，哈哈

![image.png](https://img-blog.csdnimg.cn/img_convert/1c002368a575d629d5e8c5aee6577eaa.png)

接下来的两项配置走默认，无需配置，如下图：

![image.png](https://img-blog.csdnimg.cn/img_convert/014244463f592038dfbfe7d526ab279d.png)

终于到了激动人性的时刻，我们马上就会拥有属于自己的VPS，点击Deploy Now
![Deply Now](https://img-blog.csdnimg.cn/img_convert/414af761b57053c2dbb76a499fcd688c.png)


VPS安装中
![image.png](https://img-blog.csdnimg.cn/img_convert/c649b890427cfa6e37d8386021ae3cac.png)

VPS安装完成，运行中
![image.png](https://img-blog.csdnimg.cn/img_convert/0a4c1900d0d89702f0a9adfb6cfe91a7.png)

# 七、VPS的可访问性确认

VPS虽然创建好了，但有比较小的几率访问不通，所以需要确认，确认的方式就是利用ping命令的方式，流程细节如下：

点击```...```，打开VPS操作面板，有VPS详情、VPS重启、VPS销毁等操作，如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/df45a9c37609fa633b1d1a0f2b78fac7.png)

点击```Server Detail```，展示了VPS的信息详情，具体介绍如下图:
![image.png](https://img-blog.csdnimg.cn/img_convert/851f08c8ab8f3bd5b5df1995d6d0a1e6.png)

复制IPV4地址，打开CMD窗口，执行命令，我申请的VPS IP是：```45.76.180.255```，则命令是```ping 45.76.180.255```，结果如下图：

![image.png](https://img-blog.csdnimg.cn/img_convert/f40716e862dcef954179e2d83ccece2b.png)

如若访问不通，则需要将该VPS销毁重建，IP会自动改变

# 八、优雅的连接Vultr VPS
网上很多文章采用的都是Xshell或者Putty来连接VPS，而博主不一样，博主有完美强迫症，用的工具好用还得好看才行，于是找啊找，找到一个集功能与颜值于一身的VPS连接软件，关键还**开源免费**呢~
![Tabby启动图](https://img-blog.csdnimg.cn/img_convert/4e408e6677ba1a098753abf8f701522a.png)


官方网站：[Tabby](https://tabby.sh/)

鉴于小伙伴们访问Github的速度可能比较慢，我在这里贴出来了MacOS和Windows的下载地址

[Tabby Windows X64下载](https://share.weiyun.com/x0eMqqi7)

[Tabby Mac OS下载](https://share.weiyun.com/HxZhHG8d)

不是上述版本的小伙伴，下面是官方全部版本的下载地址：[Tabby 官方全部版本下载页](https://github.com/Eugeny/tabby/releases/tag/v1.0.183)

下载安装完成后，打开后会进入设置界面，语言选择中文简体，其它默认即可，然后点击```Close and nerver show ageain```，如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/616cffd51504c47c2a0cde4e0c29ca7d.png)

接着点击```设置```，如下图
![image.png](https://img-blog.csdnimg.cn/img_convert/86c20475e3b66ad1f6d3ae3b8e39de0a.png)



选择```配置和连接```-> ```新配置```，如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/28efa9e01d57aa6f08a2ebe35b142c99.png)


选择SSH连接，如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/02754b6dd2f7a61835cf4f9cf211f52b.png)

配置Vultr VPS的SSH，配置完成后点保存，如下图：
![image.png](https://img-blog.csdnimg.cn/img_convert/1f729a195df4f41bad720d7168ac4046.png)

接着启动连接VPS，如下图:
![image.png](https://img-blog.csdnimg.cn/img_convert/c178e82d377bff2e7fd50536bcddcec9.png)


接着会弹出来框【主机密钥校验】，选择【接受并记住密钥】，如下图
![image.png](https://img-blog.csdnimg.cn/img_convert/6fc11ee39b0ba54d3c79e64cfd2baa28.png)

登录成功，见下图
![image.png](https://img-blog.csdnimg.cn/img_convert/edd5b568b274423ef9d9b32205588d12.png)





# 九、总结
为了保证教程的可行性，博主的教程都是实操。并且在做的过程会考虑一些不好理解的点，利用现实生活中的例子去阐述它，让小伙伴们知其然并知其所以然。

后续会陆续开放VPS实战篇【超详细系列 - 利用VPS搭建个人博客】、【超详细系列 - 利用VPS搭建个人网盘，自由自在存储小视频】
以及【超详细系列 - 利用VPS搭建自己的私有请求链】

若文章中有错误或者不好理解的地方，希望小伙伴们在下面留言，我看到后会及时改正，让我们一起维护【超详细系列】吧 ~

最后觉得文章还不错的话，帮忙点个赞哦~

