
使用搬瓦工VPS不仅能够科学管理自己的服务器空闲资源，还可以用来搭建一个属于自己的WordPress博客。域名后缀如今种类繁多，价格相对也十分便宜。准备一个合适的域名，即可轻松开启你的WordPress博客之旅！

👉 [【建议收藏】2025年搬瓦工最新优惠套餐整理汇总 - 每日更新最新可用优惠码](https://bit.ly/banwagon)

---


首先，你需要一台搬瓦工VPS。如果你还没有购买VPS，可以前往搬瓦工官网选择适合自己的套餐。在购买完成后，我们需要为其搭建一个建站环境。

---


完成建站环境的搭建后，就可以在环境中添加新的网站了。以下是以 LAMP 一键安装包为例的操作步骤：

bash
root@cn2:~# lamp add  # 添加网站
Please enter server names(example: www.lamp.sh lamp.sh): cn2.myblog.com  # 输入域名
Please enter website root directory(default:/data/www/cn2.myblog.com): 
Please enter Administrator Email address:  ## 输入邮箱
Administrator Email address:
Do you want to create a database and mysql user with same name? [y/n]:y  # 添加数据库
Please enter your MariaDB root password:  # 输入之前设置的数据库密码
Please enter the database name:cn2wordpressdb  # 输入数据库名称
Please set the password for user cn2wordpressdb:  # 设置数据库密码
Virtual host [cn2.myblog.com] has been created
Website root directory is: /data/www/cn2.myblog.com
Database [cn2wordpressdb] and mysql user [cn2wordpressdb] has been created
Reloading the apache config file...
Syntax OK
Reload success
Do you want to add a SSL certificate? [y/n]:n  # 是否添加SSL证书，我选了否
Do not add a SSL certificate
All done

在完成上述操作后，网站的根目录一般会位于 `/data/www/cn2.myblog.com`。进入该目录并将 WordPress 文件上传至此即可。

进入目录的命令如下：

bash
cd /data/www/cn2.myblog.com

此时，你可以利用工具如 Xftp 进行文件传输，或直接通过 `wget` 命令下载 WordPress 安装包。如果 VPS 上未安装 zip 工具，请先进行安装。

完成后，网站目录结构如以下所示：

bash
root@cn2:/data/www/cn2.myblog.com# ls
index.php    wp-activate.php     wp-comments-post.php  wp-cron.php        wp-load.php   wp-settings.php   xmlrpc.php
license.txt  wp-admin            wp-config-sample.php  wp-includes        wp-login.php  wp-signup.php
readme.html  wp-blog-header.php  wp-content            wp-links-opml.php  wp-mail.php   wp-trackback.php

确保文件权限设置正确，输入如下命令为网站目录赋权：

bash
chown -R apache:apache cn2.myblog.com  # 将域名换成实际的域名

---


在服务器配置完成后，你需要对域名进行 DNS 解析。例如，可以选择使用 dnspod 的 DNS 服务（域名需提前注册并购买）。在域名注册商处，将 nameserver 修改为如下所示：

f1g1ns1.dnspod.net
f1g1ns2.dnspod.net

然后，在 dnspod 平台添加你的域名解析记录，分别为 `www` 和 `@`，记录值设置为你的 VPS 的 IP 地址。保存后，你已完成域名解析的设置。

---


打开你的域名地址，你将看到 WordPress 的初始安装界面。点击“现在就开始！”按钮，根据提示填写数据库名、用户名和密码等相关信息。

- 数据库名、用户名和密码为之前在添加网站时设置的；
- 数据库主机和表前缀保持默认即可。

配置完成后提交数据，接着点击“进行安装”。在接下来的界面中填写站点信息：

- 站点标题：根据你的需求填写；
- 用户名和密码：用于登录网站后台；
- 电子邮件地址：请填写有效邮箱；
- 搜索引擎可见性：可选择默认不勾选。

完成后，点击“安装 WordPress”，你便可以进入 WordPress 的后台管理系统了。

---


在 WordPress 的管理后台中，可以根据需要发布文章、添加页面、安装和更换主题、配置插件等功能。至此，整个博客搭建流程大功告成。

---

心动了吗？赶紧计划你的 WordPress 博客吧！搬瓦工 CN2（DC8）机房的 VPS 性能稳定且性价比高，值得体验！
