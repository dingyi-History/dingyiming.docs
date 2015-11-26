# 1.删除Apache
```
sudo service apache2 stop
update-rc.d -f apache2 remove
sudo apt-get remove apache2
```
删除完之后，更新一下包列表
`sudo apt-get update`

# 2.Nginx
* 安装
```
sudo apt-get install nginx
```
* 使用
```
sudo service nginx start //启动
sudo service nginx restart //重启
sudo service nginx status //查看状态
```
在浏览器地址栏输入公网IP，你就可以看的welcome to Nginx的界面了

# 3.PHP
* 安装
```
sudo apt-get install php5-fpm php5-cli php5-mcrypt
```
* 配置
```
sudo vim /etc/php5/fpm/php.ini
//打开PHP配置文件，找到cgi.fix_pathinfo选项，去掉它前面的注释分号;，然后将它的值设置为0,如下

cgi.fix_pathinfo=0
5.启用php5-mcrypt:
sudo php5enmod mcrypt
6.重启php5-fpm:
sudo service php5-fpm restart
在搭建完LEMP环境之后，首先要明确两个重要目录
