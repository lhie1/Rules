# 使用手册

### 简介

本项目最早是 Fork [scomper/surge.conf](https://gist.github.com/scomper/915b04a974f9e11952babfd0bbb241a8) 定制修改而来。

---
* [兼容](#application)
	* Surge
	* Shadowrocket
	* Quantumult
* [可实现功能](#function)
* 导入方式
    * [URL](#remote-files)
    * [JSBox](#jsbox)
* [证书的安装及信任](#mitm-1)
* [Android SSR ACL](#android-ssr-acl)
* [浏览器广告](#browser-ads)
* [关于](#关于)
* [Q&A](#qa)
* [客户端](#客户端有r标示表示支持-ssr)
* [教程/说明](#教程--说明)
* [配置文件样例](#配置文件样例)
* [鸣谢](#鸣谢)
* [License](#license)

---

### Application

Configuration | Source | Group
----|----|----
Rules | [Rules Channel](https://t.me/RuleNews) | [Rules](https://t.me/lhie1x)
Surge | [@lhie1](https://t.me/lhie1) | [Surge](https://t.me/loveapps)
Shadowrocket | [@lhie1](https://t.me/lhie1) | [Shadowrocket](https://t.me/ShadowrocketApp)
Quantumult | [@Jacky Y](https://t.me/WatanabeMayu) | [Quantumult](https://t.me/quantumultapp)

---

### Function
- [x] 自动代理 / 全局代理
- [x] 解决本地 DNS 可能带来的干扰
- [x] 解决部分网站跳转问题
- [x] 可突破部分内网限制（公司、学校）
- [x] 拦截部分挖矿 JS 插件
- [x] 拦截常用应用程序及网页的行为分析
- [x] 拦截常用应用程序及网页的数据统计
- [x] 拦截常用应用程序及网页的隐私跟踪
- [x] 拦截各大购物网站的运营商劫持
- [x] 拦截 Content Security Policy 劫持
- [x] 拦截 CNNIC 根证书劫持
- [x] 屏蔽部分应用程序的启动广告
- [x] 屏蔽部分运营商劫持网页弹出的流量统计
- [x] 屏蔽部分运营商劫持网页弹出的漂浮球广告
- [x] 屏蔽常用视频广告
- [x] 屏蔽常用网站广告、其他流媒体网站广告
- [x] 屏蔽法轮功等反华势力网站
- [x] 所有国内网站直线连接
- [x] Apple 服务加速（App Store、Apple Music、Apple流媒体、iCloud备份、iCloud Drive、iTunes 等）
- [x] 国外常用网站加速（Google/Youtube/Twitter/Facebook/instagram/wikipedia/Github 等）

---

### JSBox

````
Surge：https://xteko.com/redir?name=Rules-lhie1&url=https://raw.githubusercontent.com/Fndroid/jsbox_script/master/Rules-lhie1/.output/Rules-lhie1.box
````

---

### Remote Files

````
Shadowrocket：https://raw.githubusercontent.com/lhie1/Rules/master/Shadowrocket.conf


Quantumult_Filter：https://raw.githubusercontent.com/lhie1/Rules/master/Quantumult/Quantumult.conf

Quantumult_Rejection：https://raw.githubusercontent.com/lhie1/Rules/master/Quantumult/Quantumult_URL.conf
````

---

### MitM

简介：MitM（即 Man-in-the-middle attack，用于解密 HTTPS 的流量）

iOS：
````
iOS 9 以上的系统都需要在安装证书后到关于本机里信任证书才可使其证书有效。

1. 安装：
* Surge：配置 - 编辑配置 - HTTPS 解密 - 安装证书
* Shadowrocket：配置 - 选中Shadowrocket.conf编辑配置 - HTTPS解密 - 开启HTTPS解密 - 安装证书
* Quantumult：Settings - HTTPS - HTTPS Decryption

2. 信任：
设置 - 通用 - 关于本机 - 证书信任设置 - 信任

备注：只需要安装并信任一次，使用 JSBox 升级规则丝毫不会影响证书。
备注：不要自己去生成新证书，会导致规则与证书不匹配导致 MitM 失效直接导致无法加载的问题，导出规则后直接安装并信任就可以了。如果不小心点到了，重新运行 JSBox 导出规则即可正确安装。
````

macOS：

![](https://raw.githubusercontent.com/lhie1/Rules/master/images/macOS_MitM.jpg)

---

### 关于

Rules（规则讨论/交流）：[https://telegram.me/lhie1x](https://telegram.me/lhie1x)

规则更新通知（新特性/教程/说明）：[http://t.me/RuleNews](http://t.me/RuleNews)

---

### Android SSR ACL
项目主页：https://github.com/ACL4SSR/ACL4SSR

````
1. banAD.acl（默认代理）去广告+局域网直连+国内IP段直连+国内常用域名直连+国外代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/banAD.acl
	
2. gfwlist-banAD.acl（默认直连）去广告+局域网直连+国外gfwlist列表代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/gfwlist-banAD.acl
	 
3. onlybanAD.acl（默认代理）去广告+局域网直连+全局代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/onlybanAD.acl
	
4. fullgfwlist.acl（默认直连）国外gfwlist列表代理，没有去广告，没有白名单（原版SS可直接复制文件内容使用）
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/fullgfwlist.acl
	
5. backcn-banAD.acl（默认直连）去广告+国内IP段代理+国内常用域名代理+局域网直连+国外直连
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/backcn-banAD.acl
````
---

### Browser Ads
````
Adguard：https://adguard.com/en/welcome.html
````
---

### Q&A

#### Surge 开启共享模式
````
Surge 在增加了代理共享模式，只需要开启就能让 Wi-Fi 网络中的其他设备通过这台 iPhone 代理访问网络

到高级设置中开启 Allow Wi-Fi Access ，或者直接修改配置文件，添加一行参数 allow-wifi-access = true

其他 Wi-Fi 网络环境下的设备可以输入已经开启共享代理的 Surge 设备的 IP 地址和端口号，（技巧：Surge Log 中能看到开启后本机的 IP 地址和监听端口）将 IP 地址填写到需要共享设备的 Wi-Fi 信息的 HTTP 代理里即可
````

#### 🍃 Proxy & 🍂 Domestic & ☁️ Others & 🍎 Only
````
🍃 Proxy：管控国外的流量；🚀 Direct - 直连，不可访问外网；代理服务器 - 可访问外网

🍂 Domestic：管控国内的流量；🚀 Direct - 智能分流 (Pac)；🍃 Proxy - 全局代理

☁️ Others：掌控规则名单外的非国内 IP 的流量

🍎 Only： 管控苹果的流量；如果苹果某些服务直连困难，设其为代理，可能会改善一些问题：🍎 Only - 代理服务器

建议 ： 🍃 Proxy - 代理服务器；🍂 Domestic - 🚀 Direct ；☁️ Others - 🍃 Proxy ；🍎 Only - 🚀 Direct / 代理服务器
````

#### 🏃 Auto
````
测试结果仅供参考，无法检测出 VPS 的带宽

请不要使用 google.com 作为测试目标，有可能导致 proxy 服务器 ip 被加入黑名单，导致各种操作需要输入验证码
目标 URL 对所有的 policy 是基本公平的，所以请选择像 gstatic.com 这样的在全球都有节点的 URL 作为测试目标
作者建议：http://www.gstatic.com/generate_204
````

#### 广告屏蔽未生效
````
绝大多数广告在未开启 Surge/Shadowrocket 时已经缓存到本地，广告屏蔽非立即生效，一般清理缓存就可以，部分应用需要卸载重装。
````

#### 耗电
````
当开启此类应用之后，由于所有的网络通信都被此类软件接管，所以所有的网络通讯耗电（如 WiFi、4G）都被计算在了此类应用上，使得此类软件在电量统计中占比很高。
但实际上，开启此类应用对电量消耗不会有显著影响。
````

#### 规则数量会对耗电、内存、速度产生影响吗？
````
不会，此类应用每次加载规则时都会生成一棵搜索树，可以理解为对主机名从后往前的有限状态机 DFA，并不是逐行匹配，并且对每次的匹配结果还有个哈希缓存。换句话说，2000 行的规则和 50 行的规则均为同一量级的时间复杂度 O(1)。
````

#### Surge 2 提示激活过多设备
````
Surge 2的防盗版策略为单次购买后，在最近 180 天内，若已激活的设备数量超过 10 台，则将拒绝激活新设备（家庭共享将共享购买者账号的 10 次限制）。如特殊情况请发送邮件联系作者重制。
````

#### Surge 3 提示规则过多
````
由于我维护的规则大部分用于屏蔽广告，无法进行精简，如果介意可以在通过 JSBox 生成规则时将屏蔽广告功能关闭，如果不介意请到更多 - 警告信息，关闭警告即可。
````

#### MitM 是什么？
````
用于解密 HTTPS 流量（即 Man-in-the-middle attack 简称 MitM）。
````

#### 为什么需要开启 MitM 功能？
````
屏蔽部分广告（如：新浪微博的启动广告）需要解密其 HTTPS 流量才可获取广告请求并进行拦截。
````

#### 打开某些应用（如：知乎、即刻等）无法连接？
````
检查证书，请确保已经安装证书并信任。
````

#### 为什么Surge/Shadowrocket/Quantumult 测速差距这么大？
````
Surge 是从目标 policy 返回 http response header 数据包的时间

Shadowrocket 支持两种测速方式（ICMP/TCP），默认为 ICMP 模式（即 Ping），此方法一般用来测试此服务器是否在线

Quantumult 是从目标 policy 返回 http response header 数据包的时间

准确度：Surge -> Quantumult -> Shadowrocket
````

#### 为什么 Surge 无法屏蔽优酷广告？
````
优酷为了防止广告请求被拦截，强制不通过代理访问。其他同类应用使用的是 HTTP 首包识别，所以在 TUN 模式下也能识别到该请求。Surge 是完整的 HTTP Proxy Server，在 TUN 模式下不会进行 HTTP 解析尝试。所以不会识别到这个请求。但是其他同类应用使用的方式，在 HTTP 请求使用 Keep-Alive 时可能会出现问题，无法识别到后续的请求。
````

#### 三者之间到底有什么不同？
````
功能上面大同小异，基于规则皆可达到自动分流/广告屏蔽的效果。
````

#### MitM 会影响安全（购物/网银/隐私）或性能/速度吗？
````
MitM 仅仅对预设的 Hostname 名单（公开/开源）内的地址进行 HTTPS 流量解密，不会造成安全问题，也几乎不会对性能/速度造成影响。
MitM：https://zh.wikipedia.org/wiki/中间人攻击
Surge MitM：https://medium.com/@Blankwonder/5281d8ace79d
````

#### 使用规则会影响免流（如：大王卡）吗？
````
我的规则默认自动分流（国内直连/国外代理），只要自己不对规则进行改动或改动代理模式是不会影响免流效果的。

建议（其他随意）：

🍂 Domestic - DIRECT 

☁ Other - DIRECT
````

#### 客户端（有“R”标示表示支持 SSR）：
````
• iOS

Surge：https://appsto.re/cn/D0Q_9.i

Shadowrocket (R)：https://appsto.re/cn/UDjM3.i

Quantumult（R）：https://itunes.apple.com/us/app/quantumult/id1252015438?mt=8
        
• Android

ShadowsocksR (R)：http://omgib13x8.bkt.clouddn.com/ssr-android.apk

Postern (R)：http://www.tunnel-workshop.com

• macOS

ShadowsocksX：http://omgib13x8.bkt.clouddn.com/ss-mac.zip

ShadowsocksX-R (R)：http://omgib13x8.bkt.clouddn.com/ssr-mac.dmg
        
Flora：https://github.com/huacnlee/flora-kit

Specht Lite：https://github.com/zhuhaow/SpechtLite/releases
        
Surge：http://nssurge.com

• Windows

Shadowsocks：http://omgib13x8.bkt.clouddn.com/ss-win.zip
    
ShadowsocksR (R)：http://omgib13x8.bkt.clouddn.com/ssr-win.7z

• 路由器固件

老毛子：http://www.right.com.cn/forum/thread-161324-1-1.html

梅林：http://koolshare.cn/thread-133873-1-1.html
````

---

#### 教程 / 说明：
````
Surge for iOS：https://medium.com/@scomper/a1533c10e80b
    
Surge for macOS：https://medium.com/@scomper/bb7cf735b1b8
    
Shadowrocket for iOS：http://matrix.sspai.com/p/c113cba0
    
SSR for Windows：https://ocvpn.wordpress.com/2016/10/15/shadowsocksr-for-windows设置教程
    
SSR for Android：https://yhyy135.github.io/how-to-use-ssr-android/
````

---

### 鸣谢
* @Eval](https://twitter.com/OAuth4)
* @Scomper](https://medium.com/@scomper)
* @Neurogram](http://www.taguage.com/user?id=181456)
* @suisr9255
* @Hackl0us
* @unknownTokyo
* @Jacky Y
* @Fndroid

---

### License
* 可以拷贝、转发，但是必须提供原作者信息，同时也不能将本项目用于商业用途。
