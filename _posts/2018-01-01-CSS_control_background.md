---
layout: article
title:  "用css控制背景图片的位置，大小"
date:   2018-01-01 23:26:50 +0800
categories: posts rwd

image:
  feature: Icon information.jpg
  teaser: Icon information.jpg  
---
本文主要是向大家介绍CSS控制图片的位置及大小的代码及主要语法。

### 1.CSS控制背景图片：
对于一个网页，我们开始设计的时候，可能没有过多的去想背景图到底是什么，因为大多都是设计背景色就可以了，原因吗，我想也很简单，因为它与前景音乐一样，对于网页的打开，速度会有一定的影响。不过对于一般的个人网站，或者个人博客而言，它对展现自己的个性，当然是不可或缺的了，当然什么都不会太过完美，有好就有坏，也就是当图像不可用但CSS可用的时候，替换内容就不会显示出来，因此，并不建议在导航按钮文本或类似的情况中使用CSS背景图片。

控制背景图片的CSS属性有很多，只要与图片的相关的，大多都会用的上。

#### (1)、背景图片的导入：
当然大家最熟悉的当然是background与background-image了。为网页设计背景图片的代码是：  

```body {background:url("d:\images\04.jpg")}``` 或者 ```body {background-image:url("d:\images\04.jpg")}```

这样的话，我们就能将想要作背景的图片导进网页里了。

#### (2)、背景图片的显示方式：
当然，只用上面的代码，是无法表达出自己想要的效果的。因为，图片小了，就会以平铺的方式，如果是大了，为显示它，就是会出现滚动条，这样多不好。因此，我们还得多其进行显示控制，也就是要用到 **background-repeat**，它是取值：

```
repeat :     默认值。背景图像在纵向和横向上平铺
no-repeat : 背景图像不平铺
repeat-x :    背景图像仅在横向上平铺
repeat-y :    背景图像仅在纵向上平铺
```
而代码，我想只要懂一点CSS的都知道，如下：

> - body {background:url("d:\images\04.jpg");background-repeat:no-repeat}

这样的话，它就是以原图像大小显示了。

#### (3)、背景图片的大小控制：
不过问题是，倘若图片过大了，又怎么办呢？对于一个好网页来说，最好不要用太大的图片，原因上面也说过了，影响打开网页的速度。我们最好还是用PS或者FireWorks处理一下。不过既然我提到了，我们也不防用CSS来实现图片大小的控制。

我想很多人会自然而然的用上如下代码：

```
<style type="text/css">
body{background-image:url("d:\images\04.jpg");width:350px;height:350px;}
</style>
```
呵呵，想法是好的，但你所用的浏览器支持吗？我想IE或者FF一定会当作没看见吧。

也许你会问，我曾经设计论坛风格时，是可以实现的啊？我想，如果只是上面的代码的话，
那是不可控制图片的，因为它只是控制BODY的大小。当然，这里也是控制不了的。如果是其它的ID标记，我想是可以控制记标记的范围大小，呵呵，当然也就不是图像的大小了。
说实话，这个问题不仅困扰着你们，同时也困扰着我。因为它只是一个属性的值，而不
是一个真正的对像。想到了用CSS控制的话，记得告诉我哦。

补充：W3C于9月10发布了一篇名为《CSS Backgrounds and Borders Module Level 3》的应文章，里面为CSS的背景加上了几个我们从未见的属性：

background-clip   ：

background-origin   ：

background-size   ：背景尺寸。

background-break   ：

虽然是有了这些属性，不过现在还没有支持它们的浏览器。真是好苦恼啊。

#### (4)、背景图片的位置控制：
背景图片，我科是导进来了，但是它的位置真有一点无法让人接受。因为它默认的是左上对齐。但是我们却不想这样子放置，那我们又该怎么办呢。不要着急，激动人心的时刻马上到来，

现在，让我们来认识一下 ```background-position``` 、```background-position-x``` 及```background-position-y```吧。

> -  **a**.基本语法:

     background-position : length || length
     background-position : position || position
     background-position-x : length | left | center | right
     background-position-y : length | top | center | bottom
	
> -  **b**.语法取值:
    
	 length :百分数 | 由浮点数字和单位标识符组成的长度值。
     position : top | center | bottom | left | center | right
	
> -  **c**.示例：
     
	 body { background-image: url("d:\images\04.jpg"); background-position: 50% 50%; background-repeat:no-repeat; } /*设置双向坐标，这时相当于完全居中*/
	 body { background-image: url("d:\images\04.jpg"); background-position-x: 50%; background-repeat:no-repeat; } /*设置双向坐标，这时相当于水平居中*/
	 body { background-image: url("d:\images\04.jpg"); background-position-y: 50%; background-repeat:no-repeat; } /*设置纵向坐标，这时相当于垂直居中*/
	 
对于取值为 length|top|center|bottom 我只写下面三个例子。

- body { background-image: url("d:\images\04.jpg"); background-position: top right; background-repeat:no-repeat;}/*设置双向坐标，这时相当于右上*/

- body { background-image: url("d:\images\04.jpg"); background-position: 50% center; background-repeat:no-repeat;}/*设置双向坐标，这时相当于中下*/

- body { background-image: url("d:\images\04.jpg"); background-position: 60px center; background-repeat:no-repeat;} /*设置双向坐标，这时相当于距左60像素下*/

说了这么多例子，我想你对于定位，有一定的了解了吧。

#### (5)、背景图片的透明设置：有的时候，我们总想着去将图片设置成透明的。


#### (6)、多幅背景图片的设置：
对于多幅背景图片的设置，我是在《超越CSS：WEB设计艺术精髓》里看到的。不过，
却又让我很遗憾，因为，目前支持一个标签内有多幅背景图片的浏览器太小了，我知道的也
只有Apple Safari 。以许你会问，这怎么可能。当你看完这个实例之后，我想你会惊讶，
“天啊，CSS3之前都只能给每个元素使用一幅图片。”如果想研究一下的话，就快快安装一
个SAFARI浏览器吧。对我而言，我相信，这是发展的趋势。总之一句话，谁解释CSS能力越
强，它就将是发展的潮流，谁俱有完美的WEB准标，谁就是明日浏览器之星。

> 代码如下：

<pre class="highlight"><code>C:\Users\me\Documents\GitHub\mygithub.github.io>git push -f origin HEAD^:master
Everything up-to-date

body {
background-image:
url("d:\mypic\001.png"),
url("d:\mypic\002.png");
url("d:\mypic\003.png");
url("d:\mypic\004.png");
background-repeat:
no-repeat,
no-repeat,
no-repeat,
no-repeat,
repeat-x,
repeat-y,
repeat-x,
repeat-y,
background-position:
top left,
top right,
bottom right,
bottom left,
top left,
top right,
bottom right,
bottom left;}

</code></pre>




###### 这篇是网上找到的解疑回答博客。
* [访问原博客请点击这里](http://blog.csdn.net/u013022210/article/details/27320781)