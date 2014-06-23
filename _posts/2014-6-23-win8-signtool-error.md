---
layout: post
title: win8 打包商店应用报签名错误 解决办法
---

在对win8 market应用进行打包的过程中常常会碰到下面这个错误：signtool error:an unexpected internal error has occurred

说来比较诡异，如果当前登录账号是中文名字就会出现这个问题，解决办法是:
> 使用**本地的管理员账户登录**，然后再次通过vs打包就不会报错了。

更加诡异的是，搜索到的msdn上的提问中中，提问者的vs版本是2012，而笔者的vs已经是2013update2了，这个问题仍没有解决。

参考链接：[msdn](http://social.msdn.microsoft.com/Forums/zh-CN/71b1336f-742d-4900-96ad-f21cafba57a1/signtool-erroran-unexpected-internal-error-has-occurred?forum=winstoreappzhcn)