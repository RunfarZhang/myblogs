# *DNS部署与安全*

---

## DNS

* Domain Name Service—域名服务
* 作用：为客户机提供域名解析服务

## 域名组成

### 域名组成概述

* www.sina.com.cn是一个域名，从严格意义上讲，sina.com.cn才可以称为域名（全球唯一），而www是主机名
* “主机名.域名”称为完全限定域名（FQDN）。一定是全球唯一的。一个域名下可以有多个主机。
* 可以使用*nslookup [域名]*来查看域名所对应的服务器。
* “bbs.sina.com.cn”, ”blog.sina.com.cn”等都归于“sina.com.cn”下。

### 域名组成

* 树形结构
  * <img src="./qmfgwhloanqrxtxibiji/SavedPics/ch10-DNS部署与安全/image-20200423174951829.png" alt="image-20200423174951829" style="zoom:50%;" />
* <img src="./qmfgwhloanqrxtxibiji/SavedPics/ch10-DNS部署与安全/image-20200423175036437.png" alt="image-20200423175036437" style="zoom: 67%;" />
* <img src="./qmfgwhloanqrxtxibiji/SavedPics/ch10-DNS部署与安全/image-20200423175151363.png" alt="image-20200423175151363" style="zoom:50%;" />

## 监听端口

* *TCP53*
* *UDP53*

## DNS解析种类

### 按照查询方式分类

1. 递归查询：客户机与本地DNS服务器之间、DNS转发器之间（所问即所答）
2. 迭代查询：按照DNS服务器与根等其他DNS服务器的解析过程（所问非所答）

* <img src="./qmfgwhloanqrxtxibiji/SavedPics/ch10-DNS部署与安全/image-20200423175621714.png" alt="image-20200423175621714" style="zoom:67%;" />
* 公司里的DNS服务器一般设为转发型服务器

### 按照查询内容分类

1. 正向解析：已知域名，解析IP
2. 反向解析：已知IP，解析域名

## 域名解析记录类型

* SOA：权威域名机构
* A：正向解析记录
* CNAME：别名
* PTR：反向解析记录
* MX：邮件交换记录
* NS：域名服务器解析

## 反向DNS

* nslookup手工解析时，会进行一个反向解析

## DNS服务器分类

* 主要名称服务器
* 辅助名称服务器
* 根名称服务器
* 高速缓存名称服务器

## 客户机域名请求解析顺序

* *DNS缓存-->本地hosts文件-->找本地DNS服务器*

## 服务器对域名请求的处理顺序

* *DNS高速缓存–>本地区域解析文件-->转发器-->根*

## 相关命令

* dns刷新命令：
  * ipconfig /flushdns

* dns显示命令：
  * ipconfig /displaydns

## 练习



* <img src="./qmfgwhloanqrxtxibiji/SavedPics/ch10-DNS部署与安全/image-20200424160701770.png" alt="image-20200424160701770" style="zoom:50%;" />

  *Vmnet 0是使用真实机的交换机，可以实现上网功能*

1. 主要DNS服务器：员工要指向DNS，练习清空DNS缓存，nslookup手工解析IP
2. 辅助DNS服务：成功更新区域解析记录
3. 反向解析
4. 别名
5. 转发器/根
6. 将xp与2003桥接能上网，部署2003DNS服务器，xp指向2003，并能实现xp正常上网。