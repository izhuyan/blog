---
title: 裴讯K2_A6版22.4.6.3刷华硕&潘多拉固件教程
tags: 
  - 裴讯k2
  - 刷机
  - 华硕
keywords:
  - 裴讯k2
  - 刷机
  - 华硕
toc: true

date: 2017-02-20 01:11:22
---
**之前撸的裴讯k2终于刷华硕固件成功了................一万只草泥马无法平复我心情！！！！！！！！**
Before lu pei - k2 finally brush asus firmware succeeded... Ten thousand grass mud horse can't calm my mood!!!!!!!!!!!!!!!!!!!!
![](http://wx2.sinaimg.cn/mw690/7095c8fbgy1fcwa99ym5sj20ep07jq32.jpg)
<!--more-->
> 1.安装Firefox(火狐)浏览器（其他浏览器可以试试，具体自测！！）
> 2.用网线将电脑与K2的Lan口连接，（能正常上网就行，不需要明白我也搞不懂）
> 3.保持K2与Internet互联网连通，PPPOE或者级联上级路由器均可。（同上）

 
# **开始：**
1.在Firefox地址栏内输入K2登录地址，登录K2管理界面，选择右上角的“定时重启路由器”。

2.点选时间中的右侧下拉，选择分钟选择框
![](http://wx2.sinaimg.cn/mw690/7095c8fbgy1fcw9szpwfyj20ks0ftq4i.jpg)
3.鼠标箭头（手势）放在05上，点击鼠标右键，在Firefox浏览器的属性框中选择“查看元素”。你会看到 <a value="05" style="color:#F08300;">05</a> 这个句子。
![](http://wx3.sinaimg.cn/mw690/7095c8fbgy1fcw9t01ye2j20lc0jdtay.jpg)
4.在“审查元素查看器”中将鼠标移动到value=“05”上，点击鼠标右键，选择“编辑HTML”。（不要搞错，是第一个05）
![](http://wx1.sinaimg.cn/mw690/7095c8fbgy1fcw9t15pouj20uz0kqq6f.jpg)
5.将“05”修改成为[05 | wget http://breed.hackpascal.net/breed-mt7620-phicomm-psg1208.bin](http://#) 之后，鼠标移动到黑框外的空白处点击鼠标左键，结束编辑。
![](http://wx2.sinaimg.cn/mw690/7095c8fbgy1fcw9t198h1j213c0c0wgh.jpg)

6.在定时重启路由器页面上选择05之后，点击“保存”。

7.返回本文方法第2步开始继续操作到第5步，在第5步中，将第一个“05”修改成 [05 | mtd unlock Bootloader](http://#) ，继续操作到第6步“保存”，看第8步。

8.返回本文方法第2步开始继续操作到第5步，在第5步中，将第一个“05”修改成 [05 | mtd -r write breed-mt7620-phicomm-psg1208.bin Bootloader](http://#) ，继续操作到第6步“保存”，路由器此时会自动重启。（如果路由器没有自动重启，说明操作过程有误，请仔细检查操作过程。）

9.拔除K2上Wan口的网线，路由器断电，持续按住路由器上的reset按钮，接通路由器电源，3秒后松开reset按钮。

10.在浏览器地址栏输入“[http://192.168.1.1](http://192.168.1.1)” 访问Breed Web。
![](http://wx1.sinaimg.cn/mw690/7095c8fbgy1fcw9t2k9nvj20yy0dugn3.jpg)
简而言之，就是打开右上角的定时重启路由器，在“5分钟”右键点击查看元素，你会看到“<a value="05" style="color:#F08300;">05</a>”这个句子。之后修改其中的“05”为以上所列的3条句子，修改完成后再左键点击保存，一直这么重复3次修改。在最后一次修改完成后路由灯会变红灯，意味着路由器正在重启。此时拔掉wan口网线和电源线。然后就可以先按住reset.接通电源持续按住reset5秒开机，修改本地网关为192.168.1.1就可以进入breed界面了


### 3个句子分别是：


1. 05 | wget http://breed.hackpascal.net/breed-mt7620-phicomm-psg1208.bin

2. 05 | mtd unlock Bootloader

3. 05 | mtd -r write breed-mt7620-phicomm-psg1208.bin Bootloader


## 进入到Breed Web后
![](http://wx1.sinaimg.cn/mw690/7095c8fbgy1fcw9t2k9nvj20yy0dugn3.jpg)

刷入测试版V22.4.2.8或者V22.4.2.9固件
工具下载（和谐请去谷歌）：链接: http://pan.baidu.com/s/1kVPlKgB 密码: rv37
![](http://wx4.sinaimg.cn/mw690/7095c8fbgy1fcw9t28011j20vz0ctjs1.jpg)
成功后访问p.to
![](http://wx3.sinaimg.cn/mw690/7095c8fbgy1fcw9t2ldojj20fe0680sw.jpg)
## 刷入 breed 和 ssh：

1：点击下面下载文件
下载（无需解压）：http://tianbao.sf.net/b/ (部分地区域名被DNS污染, 无法访问请使用备用链接)
备用链接：链接: http://pan.baidu.com/s/1mhEKfNU 密码: 7ijw  （解压使用）

2：登陆路由器
（默认 p.to  或者 phicomm.me 或者 192.168.2.1 或者 192.168.123.1）
3：进入： 高级设置—-系统设置—-备份恢复—-浏览—–选择下载的tianbaoha_breed_ssh.dat—-点击恢复备份—-等待进度条完成(大约需要2分钟)。
![](http://wx1.sinaimg.cn/mw690/7095c8fbgy1fcw9t41arcj20j60apjrr.jpg)

等待重启完成，大概需要2分钟


4：重启以后使用新的管理密码：tianbaoha 登陆，如果登陆成功就说明breed和ssh刷好了。

5： 进入 ：高级设置—-系统设置—-手动升级—- 点击下载备份EEPROM
![](http://wx1.sinaimg.cn/mw690/7095c8fbgy1fcw9t1kgzyj20rm0hegok.jpg)

如果继续使用斐讯固件自己改个密码就行了，如果想刷第三方固件就：

最新华硕固件: 链接: http://pan.baidu.com/s/1geZnaz5 密码: mdex

> 华硕固件默认配置
> 旧固件网关：192.168.1.1
> 新固件网关：192.168.123.1
> 管理页面：http://my.router/
> 管理账号：admin/admin
> wifi:1234567890
> 刷机不恢复默认值

潘多拉固件：链接: http://pan.baidu.com/s/1nvKy4mX 密码: w5p7

> 账号/密码 ： root/admin


点击 浏览—–选择需要刷入的固件—-点击升级即可。


参考文章：
http://www.right.com.cn/forum/thread-207852-1-1.html
http://51.ruyo.net/p/2245.html
感谢：[如有乐享](http://51.ruyo.net)，[恩山无线论坛](http://www.right.com.cn)，[Leonn_Li](http://liyuans.com) （排名不分先后）
