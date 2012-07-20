---
layout: post
title: '如何在chrome中禁用相同来源的方法'
permalink: /2012/7/20/how-to-disable-same-origin-policy-in-chrome/

---

原文链接:[Joshua McGinnis](http://joshuamcginnis.com/2011/02/28/how-to-disable-same-origin-policy-in-chrome/)

翻译:[Link](http://tachikoma.me/about)

在过去的一周,我一直在做一些浏览器的扩展开发,你可能会或者可能不知道,Chrome扩展允许跨域ajax调用.这是允许的,因为chrome扩展权限模型需要用户在安装扩展时同意安装程序可能会访问您的数据域的问题.

然而,在默认情况下,扩展只有在安装后和激活(意思是点击工具栏上扩展的图标)时才有用.

如果你正在开发一个扩展,这意味着你必须不断刷新扩展然后点击按钮以测试你的XHR请求.

事实证明,你可以启动拥有两个标记的Chrome,它将允许你轻松地浏览到您的文件直接和执行跨域调用XMLHttpRequest.

为了快捷方便,我在桌面上创建了一个增加了标记组件的快捷方式.你的快捷方式看起来应该像这样:

	C:\Users\YOUR_USER\AppData\Local\Google\Chrome\Application\chrome.exe 
	--allow-file-access-from-files --disable-web-security
	
####标记

你会注意到这两个标记加入了快捷方式的路径里.

**–allow-file-access-from-files**

**–disable-web-security**

这些标记都将允许开发人员测试跨域ajax请求的本地文件.

PS:我称这个拓展为"无担保的Chrome",所以我不会冒险总是运行带有这些标记的Chrome.

译者注:Linux或者Mac用户添加启动参数方法见["如何给mac os x下的应用程序加上启动参数"](http://www.xuanyu.net/2011/11/%E5%A6%82%E4%BD%95%E7%BB%99mac-os-x%E4%B8%8B%E7%9A%84%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F%E5%8A%A0%E4%B8%8A%E5%90%AF%E5%8A%A8%E5%8F%82%E6%95%B0.html)