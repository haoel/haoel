

# 科学上网

作者：左耳朵 [http://coolshell.cn](http://coolshell.cn)
更新时间：2018-11-29

这篇文章可以写的更好，欢迎到 [https://github.com/haoel/haoel.github.io](https://github.com/haoel/haoel.github.io) 更新

![](./images/cover.jpg)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

  - [0. 序](#0-%E5%BA%8F)
  - [1. 英文能力](#1-%E8%8B%B1%E6%96%87%E8%83%BD%E5%8A%9B)
  - [2. 购买VPS](#2-%E8%B4%AD%E4%B9%B0vps)
     - [2.1 常规VPS](#21-%E5%B8%B8%E8%A7%84vps)
     - [2.2 CN2 线路](#22-cn2-%E7%BA%BF%E8%B7%AF)
  - [3. 搭建 Shadowsocks 和 VPN 服务](#3-%E6%90%AD%E5%BB%BA-shadowsocks-%E5%92%8C-vpn-%E6%9C%8D%E5%8A%A1)
     - [3.1 设置Docker服务](#31-%E8%AE%BE%E7%BD%AEdocker%E6%9C%8D%E5%8A%A1)
     - [3.2 开启 TCP BBR 拥塞控制算法](#32-%E5%BC%80%E5%90%AF-tcp-bbr-%E6%8B%A5%E5%A1%9E%E6%8E%A7%E5%88%B6%E7%AE%97%E6%B3%95)
     - [3.3 设置Shadowsocks服务](#33-%E8%AE%BE%E7%BD%AEshadowsocks%E6%9C%8D%E5%8A%A1)
     - [3.4 设置L2TP/IPSec服务](#34-%E8%AE%BE%E7%BD%AEl2tpipsec%E6%9C%8D%E5%8A%A1)
     - [3.4 设置PPTP服务](#34-%E8%AE%BE%E7%BD%AEpptp%E6%9C%8D%E5%8A%A1)
  - [4. 客户端设置](#4-%E5%AE%A2%E6%88%B7%E7%AB%AF%E8%AE%BE%E7%BD%AE)
     - [4.1 Shadowsocks 客户端](#41-shadowsocks-%E5%AE%A2%E6%88%B7%E7%AB%AF)
     - [4.2 VPN 客户端](#42-vpn-%E5%AE%A2%E6%88%B7%E7%AB%AF)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## 0. 序

首先，我们先明确一下，科学上网的目的主要是为了学习、工作、交友、查资料、和丰富自己的眼界，不是为了看黄片和任何地下见不得人的东西。

下面罗列一下需要科学上网，我才能真正学习工作和生活的网站：

- Youtube 和 Vimeo 上的各种大会和教学视频，除了我自己要学，我的孩子也要学。
- Wikipedia 维基百科是我目前唯一信得过的百科全书，我在上面可以比较系统地翻阅各种词条。
- Slideshare 上有很多的技术文档和资料的PPT，是我的知识学习的地方。
- Quora 问答网站，在上面有很多有趣的问答。
- 博客和论文，很多博客和论文站点都被墙了，比如：Blogspot 和 Medium。
- Google 的各种服务，比如：Gmail, Map, Docs，Driver，照片，图片搜索，Voices，论文搜索……包括Google官方的各种技术文档……
- 一些云服务，比如：Dropbox，IFTTT，Imgur，archive.org……
- Twitter 上 Follow 一些牛人和一些官方账号，比如：AWS、Docker……
- 社交 Facebook, Telegram, Whatsapp，Slack…… 有一些我在国外的亲戚和朋友……
- Reddit 是一个聚合网站，一个新闻和文章的集散地，你可以认为是各种频道的今日头条……
- Pintrest 和 Instagram  上面有很多不错的图片和视频新闻，是我减压力的地方……
- 新闻，如BBC。 BBC是全球最比较出众的媒体，其上有太多的有价值资源和内容了，比如纪录片……
- 编程，有很多编程的场景需要翻墙，比如，Go语言编程时的 go get 中的很多库是放在 Google的服务器上， 然而Google是全部被墙，包括 Android 和其它一些文档和资源也是一样。包括 SourceForge 的某些项目也需要科学上网，Docker Registry也有部分被墙，还有偶尔抽疯的Github……
- ……等等

是的，我的互联网不是——全是骗子的百度、充满广告的微信朋友圈、质量低下的公众号、娱乐至死的新浪微博、只有抖机灵和“怎么看”的知乎、毫无营养的今日头条…… 在这样的网络空间里，我真的无法生存…… 这根本不是互联网，不是为我服务的互联网，而是在消费我的互联网，是让我变傻变笨的互联网…… 我不能忍，因为它影响到了我的生存……


## 1. 英文能力

**首先，你应该对英文读写没什么问题!**

为什么这么说？**逻辑是这样的，如果你上了Google还是在用中文关键词，那么你科学上网有什么意义呢？** 换言之，科学上网的目的是为了进入广阔的世界范围与全世界的人交流，所以，英文是必备的，如果你英文有问题，VPN过去的用处也不大。

所以，我把这个前提条件放在第一的位置，就是说—— **真正的墙不是GFW，而是人的大脑！**


## 2. 购买VPS

然后，你需要一个VPS。 

（注：*当然，你也可以直接购买一些科学上网的服务，但我这里不推荐了，一方面是广告，另一方面可能会害了对方*）

**现在你买一台VPS也不贵了，也就是一个月10美金左右（70元），我个人一个月你花70元钱不算奢侈的事，而且会让你的生活质量得得改善**。

### 2.1 常规VPS

对于VPS，下面是一些常规选项。

- [AWS](https://aws.amazon.com/cn/)日本或韩国申请个免费试用一年的EC2 VPS （需要国际信用卡）
- [Linode](https://www.linode.com)买个一月USD10刀的VPS
- [Vultr](https://www.vultr.com)上买一个日本的VPS，一个月5刀 （可以支付宝）
- [Conoha](https://www.conoha.jp/zh/)上买一个日本的VPS，一个月900日元 （可以支付宝）

注意，日本区的网络质量并不是很好，有时候会有很大的丢包率（不同的网络不一样），有时候会很慢。上述的这几个VPS服务商中，AWS韩国和日本会好点，然后是Linode，最后是Conoha和Vultr（如果你有更好的，请推荐）

### 2.2 CN2 线路

如果你需要更好更高速的网络服务（比如你要看Youtube的1080P），那么，你需要下面的这些服务器资源了（价格也会高一些）

`CN2` 和 `GIA` 是两个关键词。**CN2 GIA** 全称 China telecom Next Carrier Network- Global Internet Access 电信国际精品网络，特征是路由线路上骨干节点均为59.43开头的IP。如果想要寻找接入CN2线路的国外VPS提供商，建议使用 `Next Carrier Network` 或者 `CN2` 这个关键词搜索即可。

多说一句， CN2本身又分为两种类型：

- **CN2 GT**: CN2 里属于Global Transit的产品(又名GIS-Global Internet Service)，在CN2里等级低，省级/出国节点为 `202.97` 开头，国际骨干节点有2～4个 `59.43` 开头的CN2节点。在出国线路上拥堵程度一般，相对于163骨干网的稍强，相比CN2 GIA，性价比也较高。

- **CN2 GIA**: CN2 里属于Global Internet Access的产品，等级最高，省级/出国/国际骨干节点都以`59.43`开头，全程没有`202.97`开头的节点。在出国线路上表现最好，很少拥堵，理论上速度最快最稳定，当然，价格也相对 CN2 GT 偏高。
 
关于 `CN2` 线路的主机提供商，下面罗列几个

- [搬瓦工](https://bandwagonhost.com/aff.php?aff=39384)  这应该是美区最好的一个用来科学上网的VPS提供商了，实测飞快。
- [Gigsgigscloud](https://clientarea.gigsgigscloud.com/index.php?/cart/cloudlet-v-hk/&step=0) CN2 GIA 在香港的结点是很不错的，当然，价格也很不错（建议几个人一起平摊费用）
- [Kvmla](https://www.kvmla.com/) 香港地区的CN2 GIA提供商 每月80元
- [Hostdare](https://manage.hostdare.com/index.php) 的CN2 GIA产品也是三网直连，KVM和OpenVZ两种架构，KVM产品长期缺货

更多的可以参考这篇文章《[CN2 GIA VPS主机收集整理汇总-电信,联通,移动三网CN2 GIA线路VPS主机](https://wzfou.com/cn2-gia-vps/)》

重点说一下，**CN2 GIA + 香港机房**，你会得到巨快无比的上网速度，然而，香港地区的VPS的确是有点贵了。在Youtube.com上看1080p的视频毫无压力。虽然阿里云和腾讯的也有，但是被查到的风险基本上是100%，不建议使用，被抓了别怪我没警告过你。



## 3. 搭建 Shadowsocks 和 VPN 服务

### 3.1 设置Docker服务

首先，你要安装一个Docker CE 服务，这里你要去看一下docker官方的安装文档：

- [CentOS 上的 Docker CE 安装](https://docs.docker.com/install/linux/docker-ce/centos/)
- [Ubuntu 上的 Docker CE 安装](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

然后开始设置你的VPN/SS服务

### 3.2 开启 TCP BBR 拥塞控制算法

TCP BBR（Bottleneck Bandwidth and Round-trip propagation time）是由Google设计，于2016年发布的拥塞算法。以往大部分拥塞算法是基于丢包来作为降低传输速率的信号，而BBR则基于模型主动探测。该算法使用网络最近出站数据分组当时的最大带宽和往返时间来创建网络的显式模型。数据包传输的每个累积或选择性确认用于生成记录在数据包传输过程和确认返回期间的时间内所传送数据量的采样率。该算法认为随着网络接口控制器逐渐进入千兆速度时，分组丢失不应该被认为是识别拥塞的主要决定因素，所以基于模型的拥塞控制算法能有更高的吞吐量和更低的延迟，可以用BBR来替代其他流行的拥塞算法，例如CUBIC。Google在YouTube上应用该算法，将全球平均的YouTube网络吞吐量提高了4%，在一些国家超过了14%。

BBR之后移植入Linux内核4.9版本，并且对于QUIC可用。

如果开启，请参看 《[开启TCP BBR拥塞控制算法](https://github.com/iMeiji/shadowsocks_install/wiki/开启TCP-BBR拥塞控制算法) 》

### 3.3 设置Shadowsocks服务

Shadowsocks 的 Docker 启动脚本 （其中的 `SS_PORT` 和 `SS_PASSWD` 需要重新定义一下）


```
#!/bin/bash

SS_PORT=1984
SS_PASSWD=MyPasswd

sudo docker run -dt --name ss \
   -p ${SS_PORT}:${SS_PORT} mritd/shadowsocks \
   -s "-s 0.0.0.0 -p ${SS_PORT} -m aes-256-cfb -k ${SS_PASSWD} --fast-open"
```


### 3.4 设置L2TP/IPSec服务

L2TP/IPSec 的启动脚本，其中的三个环境变量 `USER`， `PASS` 和 `PSK` 需要替换一下。

```
#!/bin/bash

USER=someone
PASS=password
PSK=psk_key

sudo docker run -d  --privileged \
    -e PSK=${PSK} \
    -e USERNAME=${USER} -e PASSWORD=${PASS} \
    -p 500:500/udp \
    -p 4500:4500/udp \
    -p 1701:1701/tcp \
    -p 1194:1194/udp  \
    siomiz/softethervpn
```

### 3.4 设置PPTP服务

PPTP不安全，请慎重使用

```
sudo docker run -d --privileged --net=host 
                -v {/path_to_file/chap-secrets}:/etc/ppp/chap-secrets \
                mobtitude/vpn-pptp
```
PPTP 使用 `/etc/ppp/chap-secrets` 文件设置用户名和密码，所以你需要给docker容器提供这个文件，下面是这个文件的示例：

```
# Secrets for authentication using PAP
# client    server      secret           acceptable local IP addresses
  fuckgfw   *           whosyourdaddy    *
```


## 4. 客户端设置

### 4.1 Shadowsocks 客户端

对于 Shadowsocks 客户端，可以到这里查看 [Shadowsocks Clients](https://shadowsocks.org/en/download/clients.html)

- MacOS 上你可以下载 [ShadowsocksX-NG](https://github.com/shadowsocks/ShadowsocksX-NG/releases)
- Windows上你可以下载 [Shadowsocks-Windows](https://github.com/shadowsocks/shadowsocks-windows/releases)，需要先安装 [.NET Framework](https://dotnet.microsoft.com/download/dotnet-framework-runtime)
- Android的客户端，你可以用手机访问并下载 [Shadowsocks-Android](https://github.com/shadowsocks/shadowsocks-android/releases)
- iPhone 端就比较麻烦了。因为国内全都被下架了。
	1. 你需要注册一个美国的苹果ID.
	2. 然后 iTunes/App Store 用这个美区的ID登录（不是退出iCloud ，而是退出App Store）
	3. 然后搜索 `Wingy` ，你会搜到 `OpenWingy`, `SuperWingy` 等


### 4.2 VPN 客户端

对于L2TP/IPSec，几乎所有的客户端操作系统（无论是Windows/Mac/Linux的电脑，还是iPhone/Android）都支持，你可以自行Google。

- [Mac OS X PPTP/L2TP设置教程](https://www.jianshu.com/p/24e48cfb574f)
- [Windows 7操作系统配置L2TP VPN方法](http://nic.upc.edu.cn/2016/0928/c7809a132077/page.htm)


（全文完）







