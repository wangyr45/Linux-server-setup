# Odoo
关于Odoo安装部署等一系列问题，供有缘人安装部署及服务器搭建
# 将 ODOO 安装在 Ubuntu 上面

无论用于生产环境，还是用于开发和测试环境，我们都建议将ODOO安装在 Linux 环境下，稳定性和性能都能得到保证。

ODOO 官方也给出了安装指令。补充一些官方没提到的内容，这样初学者也能根据指令完成安装。

本文举例用的是 ubuntu 16.04，安装 ODOO 10 版本。

使用 SSH 登录到远程服务器（VPS），或者打开本地方服务器的终端。按如下步骤执行指令：

1、更新系统（碰到问 Y/n的地方，一律 Y，下同）

```
sudo apt-get update && sudo apt-get upgrade
```

![1-0](http://zhflash.com/wp-content/uploads/2016/10/1-0.png)

2、安装数据库

```
sudo apt-get install postgresql postgresql-contrib
```

![2-0](http://zhflash.com/wp-content/uploads/2016/10/2-0.png)

3、安装 ODOO

```
wget -O - https://nightly.odoo.com/odoo.key | apt-key add -
echo "deb http://nightly.odoo.com/10.0/nightly/deb/ ./" >> /etc/apt/sources.list
sudo apt-get update && apt-get install odoo
```

![3-0](http://zhflash.com/wp-content/uploads/2016/10/3-0.png)

4、安装 LESS 主题引擎

```
sudo apt-get install nodejs npm
sudo npm install -g less
sudo npm install -g less-plugin-clean-css
```

![4-0](http://zhflash.com/wp-content/uploads/2016/10/4-0.png)

5、安装 PDF 生成器 wkhtmltopdf

```
sudo apt-get install libxrender1 fontconfig xvfb
wget http://download.gna.org/wkhtmltopdf/0.12/0.12.3/wkhtmltox-0.12.3_linux-generic-amd64.tar.xz -P /tmp/
cd /opt/
sudo tar xf /tmp/wkhtmltox-0.12.3_linux-generic-amd64.tar.xz
sudo ln -s /opt/wkhtmltox/bin/wkhtmltopdf /usr/local/bin/wkhtmltopdf
```

![5-0](http://zhflash.com/wp-content/uploads/2016/10/5-0.png)

6、安装 nginx

```
sudo apt-get install -y nginx
```

![6-1](http://zhflash.com/wp-content/uploads/2016/10/6-1.png)

7、检查是否安装成功

![6-0](http://zhflash.com/wp-content/uploads/2016/10/6-0.png)

![6-2](http://zhflash.com/wp-content/uploads/2016/10/6-2.png)

![6-3](http://zhflash.com/wp-content/uploads/2016/10/6-3.png)
