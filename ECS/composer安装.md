> Ubuntu 安装curl ` apt-get install curl`
> $ curl -sS http://packagist.cn/composer/installer | php
>Ubuntu Composer安装

1、下载并执行Installer，要注意的是，如果沒有在php前面加上sudo的话，有可能出现错误信息。

sudo curl -sS https://getcomposer.org/installer | sudo php -d detect_unicode=Off  
2、切换到全局安装文件夹

sudo mv composer.phar /usr/local/bin/composer  
3、更改文件权限：上面的命令完成后，会下载好一个名为composer.phar的文件，而这个文件就是Composer的本体了，不过要更改一下它的权限。

sudo chmod a+x composer.phar  
4、更新：完成上面的步骤后，Composer就装好了，过一段时间Composer自身升级版本，执行下面的命令就行（一般在你更新包的时候如果Composer有新版本，会提醒你需要升级）。

sudo composer self-update
