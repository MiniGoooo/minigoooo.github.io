---
title: 还记得加的第一位QQ好友是谁吗?
date: 2017-08-09 15:25:50
tags: [QQ]
---

![banner](http://ouesmsejm.bkt.clouddn.com/blog/170810/h112bLj9L5.jpg?imageslim)

**还记得你什么时候注册的QQ嘛**？

**还记得你加的第一位QQ好友嘛**？

<!-- more -->

**按照下面步骤**

1. 点击进入： [QQ官网](http://im.qq.com/index.shtml) 
2. 点击右上角登陆，登陆进去
3. 页面鼠标右击：如图所示，点击**审核元素**

 ![mark](http://ouesmsejm.bkt.clouddn.com/blog/170809/9c44cjCc2G.png?imageslim))

4. 然后点击如图所示的**console**

 ![mark](http://ouesmsejm.bkt.clouddn.com/blog/170809/0cGda579id.png?imageslim)

5. 将下面的代码复制粘贴到图片中top字母下面的空白处，然后回车！

>$.ajax({
	url : 'https://ti.qq.com/mqqbase/cgi/medalwall/medalguide',
	dataType: 'json',
	type : 'POST',
	xhrFields: {withCredentials: true}, 
	crossDomain: true,
	contentType: "application/json",
	success:function(data){
	if(data.errCode!=0){
		alert("你没登录?");
		return;
	}
	var d=new Date();
	d.setTime(data.data.registDate);
	alert("注册时间:"+d.toLocaleString()+" 第一个添加的好友:"+data.data.firstFriend)}
	});


**如果提示没有登陆那么就退出再登陆一下**

**竟然不管用了，请求的网址应该被去掉了（404）。** 

下图是我第一次请求的效果：

 ![mark](http://ouesmsejm.bkt.clouddn.com/blog/170809/Ee7aIjLgcA.png?imageslim)