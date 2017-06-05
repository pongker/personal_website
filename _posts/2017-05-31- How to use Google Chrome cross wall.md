---
layout: post
title: 利用Google Chrome浏览器访问国外网站
date: 2017-05-31
tags: 博客
---


<br/>
如果把世界上的网站比喻成一道道门，那么浏览器就是打开这些门的钥匙。  
当然每个人对钥匙的喜好不同，每个人对浏览器的个性化需求也不同。  
Chrome浏览器由Google公司研发，体量轻巧，功能强大，这里不多安利。

目前在国内大陆安装Chrome，可能会遇到很多问题：  
Google目前还在被墙（这里给大家安利一下Google Translate）    
无法去官网直接下载Chrome浏览器，需要从第三方平台下载  
Chrome商店无法打开，Chrome无法获取版本更新    
Chrome搜索引擎无法使用，只能使用其他搜索引擎    
<br/>  

[翻墙](https://zh.wikipedia.org/wiki/%E7%AA%81%E7%A0%B4%E7%BD%91%E7%BB%9C%E5%AE%A1%E6%9F%A5/)可以解决上述问题。  但是怎么从容的优雅的翻呢？    
站在墙外说墙外只是在做无用功，本着分享精神，这里展示两种翻墙技巧。

首先，准备一个Chrome浏览器，各大平台均有下载，这里提供一个第三方平台的下载链接[百度软件中心](http://rj.baidu.com/soft/detail/14744.html?ald ).  
安装步骤这里就不再展示了，打开下载好的安装器一路往下点即可。  
安装成功后，可以运行Chrome浏览器，你将看到Google的大门为你打开。
![Google]({{site.url}}/assets/About_Chrome/google198781312.png "Welcome")
<br/>
如果对国外网站的需求不高，那么可以选择修改Chrome的hosts文件，修改成功后可以满足基本使用需求，登录Google、Facebook、Twitter等著名网站不成问题。  
有兴趣的同学可以看一看修改hosts文件的原理[hosts文件原理](https://www.zhihu.com/question/19782572)  
<br/>
**接下来是下载安装hosts的方法:**  
修改后的hosts文件网上比较多，可以自行搜索下载，也可以点击这里[Google hosts](https://laod.cn/hosts/2017-google-hosts.html)
<br/>
找到hosts之后下载到自己的电脑上  
(hosts是一个没有扩展名的系统文件,你可以选择使用记事本之类的文本编辑工具打开它[hosts]({{site.url}}/assets/About_Chrome/hosts27461494.png))
hosts下载完成后接下来需要替换进本地hosts文件。

<font color="#f4436">
      注意：这里只介绍了Windows系统hosts文件的位置</font>  
请根据下列路径查找hosts文件：
{% highlight ruby %}    C:\Windows\System32\drivers\etc\hosts  
{% endhighlight %}

找到之后，用下载好的hosts文件替换原生的hosts文件  
接下来清除掉本地的DNS缓存  
<font color="#f4436">
      Windows系统下</font>   
开始 -> 运行 -> 输入cmd -> 在CMD窗口输入  
{% highlight ruby %}
ipconfig /flushdns    #清除本地DNS缓存
{% endhighlight %}
<br/>
这样修改hosts的工作就基本完成了，可以打开Youtube尝试一下效果。

修改hosts文件比较简单，如果遇到问题，可以尝试百度。  

<br/>
**接下来介绍使用XX-Net软件 + SwitchyOmega浏览器插件的方法实现国外网访问。**  
这个方法与修改hosts文件的方法原理不同，有兴趣的同学可以看看这里[代理服务器工作原理](http://blog.csdn.net/somayuki/article/details/59189749  )
<font color ="f4436">      这里只介绍Windows系统下的安装方法。  </font>  
首先获取XX-Net软件，可以通过github搜索‘XX-Net’关键字或者其他渠道获得，这里附上一个可用下载链接[XX-Net](https://codeload.github.com/XX-net/XX-Net/zip/3.3.1)  
![unzip]({{ site.url }}/assets/About_Chrome/xx-net419841346.png "解压后的XX-Net")  
点击start.vbs或者start.bat启动软件(这里会弹出命令窗口)    
启动完毕后，会自动弹出默认浏览器并访问 http://localhost:8085/，这是XX-Net的配置界面！[配置界面简介](https://github.com/XX-net/XX-Net/wiki/%E9%85%8D%E7%BD%AE%E9%A1%B5%E9%9D%A2%E7%AE%80%E4%BB%8B)     
此时XX-Net已经安装完成，电脑桌面右下角将出现XX-Net的图标  
<br/>
接下来需要安装并设置浏览器代理插件  
打开XX-Net文件夹，找到SwitchyOmega文件，这里的crx后缀文件就是要用到的Chrome插件了。  
把SwitchyOmega.crx文件拖放到浏览器扩展程序页面安装(也可以打开Chrome浏览器 -> 设置 -> 扩展程序 -> 加载已解压的扩展程序，根据路径安装)。  
此时浏览器会弹出确认安装信息  
![添加扩展程序]({{ site.url }}/assets/About_Chrome/xx2.JPG "确认安装")  
初次使用SwitchyOmega会显示使用教程，可以点击查看    
接下来进入SwitchyOmega的选项界面，选择导入/导出选项  
![导入bak文件]({{ site.url }}/assets/About_Chrome/xx5.JPG "导入bak文件")  
点击从备份文件中恢复后，找到XX-Net/SwitchyOmega/OmegaOptions.bak文件，点击打开  
![导入bak文件]({{ site.url }}/assets/About_Chrome/xx5.5.JPG)   
到这里SwitchyOmega代理插件已经安装完成了，接下来需要更新SwitchyOmega的情景模式   
![更新情景模式]({{ site.url }}/assets/About_Chrome/f6731972-37d1-11e6-83c1-88b876f4f52d.png "立即更新情景模式")   
更新情景模式完成后回到谷歌浏览器，点击SwitchyOmega图标，勾选XX-Net自动切换选项  
![调整代理模式]({{ site.url }}/assets/About_Chrome/4949879641534874.png "选择XX-Net自动切换")  
<font color="#4caf50">现在，你可以畅游网络了。</font>  
<br/>
当然也可以部署自己的服务器。  
把Google云平台申请获得的应用ID绑定到XX-Net的部署服务器项下，就可以使用自己的流量上网了。
这需要一个Google账户[Google账号申请](https://accounts.google.com/ServiceLogin?passive=1209600&continue=https%3A%2F%2Faccounts.google.com%2FManageAccount&followup=https%3A%2F%2Faccounts.google.com%2FManageAccount)，申请流程与国内网易、腾讯等个人账户申请流程类似，这里不再多述。  
打开    [https://console.developers.google.com]()  ，这里是Google开发者界面(这里页面相应速度较慢，需要一点耐心)  
![Google developer]({{ site.url }}/assets/About_Chrome/project19841346874.png)  
![appid]({{ site.url }}/assets/About_Chrome/appid141658648678913.png)    
接下来打开XX-Net软件的配置界面
![部署服务器]({{ site.url }}/assets/About_Chrome/683e21b4-fb78-11e5-8488-dc637f292a0e.jpg)  
会自动跳转到Google账户认证授权  
![部署服务器]({{ site.url }}/assets/About_Chrome/64dbcad0-fb78-11e5-924d-ae85efd52f48.jpg)
点击确认后将跳转到新的页面并出现提示内容：   
{% highlight ruby %}
The authentication flow has completed.    #认证流程已完成
{% endhighlight %}
此时部署工作已完成。   
![部署服务器完成]({{ site.url }}/assets/About_Chrome/appid19841569849783.png)   
在这里将部署好的appid保存  
![配置保存]({{ site.url }}/assets/About_Chrome/appid1654949849879032165.png)    
设置保存成功,你可以访问真正的互联网了.

<br/>
如果部署appid有任何疑问，请访问这里[how to create my appids](https://github.com/XX-net/XX-Net/wiki/how-to-create-my-appids)   
对XX-Net的系统托盘配置不了解，可以参考这里[设置代理](https://github.com/XX-net/XX-Net/wiki/%E8%AE%BE%E7%BD%AE%E4%BB%A3%E7%90%86)  
对设置代理部分有什么问题，可以参考这里[Chrome教程](https://github.com/XX-net/XX-Net/wiki/%E4%BD%BF%E7%94%A8Chrome%E6%B5%8F%E8%A7%88%E5%99%A8)
<br/>
