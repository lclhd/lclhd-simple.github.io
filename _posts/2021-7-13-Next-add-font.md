---
title: NexT字体折腾小记
date: 2021-7-13 7:00:30
categories:
- IT
tags:
---

昨天浏览了一个网站，看到它的英文字体特别好看，查了下网页源代码，字体是[“Architects Daughter”](https://fonts.google.com/specimen/Architects+Daughter?preview.text=dauthter&preview.text_type=custom&query=architects)，是[Google fonts](https://fonts.google.com/)上的网络字体，然后我尝试在_variables/base.scss里按照Google fonts上面的指导导入这款字体：

~~~css
<link rel="preconnect" href="https://fonts.googleapis.com"> 
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin> 
<link href="https://fonts.googleapis.com/css2?family=Architects+Daughter&display=swap" rel="stylesheet"> 
~~~
设定css：
~~~css
font-family: 'Architects Daughter', cursive;
~~~

结果GitHub报错，可能是我导入的位置不对，我想看看用纯html页面能不能显示，结果还是显示不了，毕竟html和markdown还是不一样。后来，我在Google上面搜到[spartazhc](https://spartazhc.github.io/)的[这篇文章](https://spartazhc.github.io/2020/06/03/Next%E4%B8%BB%E9%A2%98%E5%AD%97%E4%BD%93%E9%85%8D%E7%BD%AE/)，提示在config.yml里的font项添加字体配置，很简单，只需要添加网络字体的host和family就好了

~~~yml
# Uri of fonts host. E.g. //fonts.googleapis.com (Default)
  host: https://fonts.loli.net
# Global font settings used on <body> element.
  global:
# external: true will load this font family from host.
  external: true
  family: "Architects Daughter"
~~~



原来Next的主题模板早就提供了字体的配置。这里有个问题困扰了我很久，我一直以单引号来引起后面带有空格的值，从来没觉得这样有什么问题，可是GitHub一直在这个地方报错，后来我不用引号，直接用单字，试了一下其他的字体，比如[Kalam](https://fonts.google.com/specimen/Kalam?query=kalam)，这个不用加引号，显示竟然没有一点问题，我意识到，问题可能还是引号的问题，看了下config.yml里面所有引用的地方用的都是双引号！我换成双引号，字体重新换成“Architects Daughter”，没有一点问题了，完美显示:joy:，正如现在看到的这样。

