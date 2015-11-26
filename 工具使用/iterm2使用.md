# 安装zsh
*  curl下载安装zsh
```
curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
```
*  mac 替换掉默认的terminal
```
  cat /etc/shells // 查看所有shell
 sudo cash -s /bin/zsh  //替换zsh为默认shell
```
# iTerm2
```
分窗口操作：shift+command+d（横向）command+d（竖向）
查找和粘贴：command+f，呼出查找功能，tab 键选中找到的文本，option+enter 粘贴
自动完成：command+ 根据上下文呼出自动完成窗口，上下键选择
粘贴历史：shift+command+h
回放功能：option+command+b
全屏：command+enter
光标去哪了？ command+/
Expose Tabs：option+command+e
```
> oh-myzsh /highlighting

* http://www.geekplux.com/2014/03/03/mac_configuration_2.html
* 高亮提示
https://github.com/zsh-users/zsh-syntax-highlighting
