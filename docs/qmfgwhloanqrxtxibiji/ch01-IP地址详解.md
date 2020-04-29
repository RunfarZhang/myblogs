## IP地址详解

---

---

### 简单局域网构成

 



* <img src="/./qmfgwhloanqrxtxibiji/SavedPics/IP地址详解/image-20200319152743288.png" alt="image-20200319152743288" style="zoom:50%;" />

* *交换机只能组建内网（局域网）、路由器只能组建外网（互联网）*

* 简单局域网构成：交换机、网线、PC
* 三层交换机：既有交换机的功能，也有路由器的功能

### IP地址

* *一个唯一标识，是一段网络编码（二进制），IPv4地址有32位*

  * **点分十进制**
  
  * <img src="/./qmfgwhloanqrxtxibiji/SavedPics/IP地址详解/image-20200319153243205.png" alt="image-20200319153243205" style="zoom:100%;" />
  * 0-255

### 子网掩码

* *局域网通信规则：在同一个局域网中，所有IP必须在同一网段中可以互相通信！*
* *IP地址构成：网络位+主机位（网络位相同的IP地址，才是同一网段）*

* *子网掩码：*
  255.0.0.0

  255.255.0.0
  255.255.255.0

### IP地址详解

* *A类：1-126 默认子网掩码：255.0.0.0*
  *B类：128-191 默认子网掩码：255.255.0.0*
  *C类：192-223 默认子网掩码：*255.255.255.0
  *D类：224-239 组播地址*
  *E类：240-254 科研使用*
* **127.0.0.1：回环地址**
* 

* 现在各类地址与子网掩码不必对应

* 虚拟机上的每个vmnet-0。。。都意味着一个交换机。

* 主机位全部置0代表当前网段名称，全部置1代表当前网段的广播地址

### 网关

* *网关：一个网络的出口，Gateway=GW，一般网关实在路由器上*
* 路由器：可用于连接外网的设备

* <img src="/./qmfgwhloanqrxtxibiji/SavedPics/IP地址详解/image-20200319160815067.png" alt="image-20200319160815067" style="zoom:67%;" />

  ---

*  <img src="/./qmfgwhloanqrxtxibiji/SavedPics/IP地址详解/image-20200319160831073.png" alt="image-20200319160831073" style="zoom:50%;" />

* *上网第一步：先比较是否在同一个局域网（网段）内。*

* ***网关地址：一般是该网段第一个或者最后一个***

### DNS

* Domain Name Service域名服务器
* 上网
  1. 找缓存
  2. 找本地解析文件
  3. 求助DNS

* 北京市联通通用DNS
  <img src="/./qmfgwhloanqrxtxibiji/SavedPics/IP地址详解/image-20200319163338093.png" alt="image-20200319163338093" style="zoom:50%;" />

* nslookup

### 配置IP地址

### 命令

#### ping

* ping -t 一直ping
* ping -n 修改包数量
* ping -l 2000 修改包大小

#### nslookup

* 手工解析域名

#### ipconfig

* 查看本机ip
* ipconfig /all 可以查看DNS