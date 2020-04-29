# *WEB服务器*

---



1. 也称为网页服务器或HTTP服务器

2. WEB服务器使用的协议是HTTP或HTTPS

3. HTTP协议端口号：TCP 80
   HTTPS协议端口号：TCP 443

   FTP：TCP 21

4. WEB服务器发布软件：

   微软：IIS（Internet Information Services）：可以发布WEB网站和FTP站点

   Linux：Apache、LAMP、Tomcat、Nginx。。。

   第三方（学习测试使用）：phpstudy、XAMPP

5. 部署WEB服务器：

   1. 配置静态IP地址
   2. 安装IIS-WEB插件
   3. 停用默认站点
   4. 新建网站-地址端口绑定-指定站点路径-设置权限
   5. 设置默认文档（首页）

   *Tips:*

    * IIS服务器默认网站的地址时：C:\Inetpub\wwwroot
    * 当所有网站服务器全部关闭时，HTTP端口自动关闭

6. 一台服务器同时发布多个WEB站点

   1. 不同IP，相同端口
   2. 相同IP，不同端口
   3. 相同IP，相同端口，不同的域名（主机头）

7. 网站类型：

   1. 静态网站：一般扩展名为.html或.htm；**无后台数据库**

      *Tips*：`<marquee>`标签可以实现内容滚动

   2. 动态网站：一般扩展名为.asp或.php

      *Tips*：一般asp只在windows里有；**有后台数据库，asp或php可以连接前台页面与后台数据库**

 
      * *在网站--属性--主目录--配置（下方）--选项（上方）--启用父路径*，这样就可以访问该站点下子文件夹。
      * 

