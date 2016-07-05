css里面单位有好几种，虽然我们习惯常用的就那几种。

用的比较多的可能是这几种：px、pt、em、rem。

这篇文章主要用来系统的学习下单位。

不同的单位使用起来有不同的利弊，我们需要知道在何时使用哪个单位最合适

# 绝对单位

## px
像素px是相对于显示器屏幕分辨率而言的。

### 利
* 一致
* 比较稳定和精确

### 弊
* 当用户在浏览器中浏览我们制作的Web页面时，他改变了浏览器的字体大小，这时会使用我们的Web页面布局被打破 => 也就是我们不太好放大缩小页面

## pt

# 相对单位

## em
相对于当前对象内文本的字体尺寸。如当前对行内文本的字体尺寸未被人为设置，则相对于浏览器的默认字体尺寸。

### 利
* 会继承父元素的字体大小
* em的并不是一直固定的

## ex

## rem
使用rem为元素设定字体大小时，仍然是相对大小，但相对的只是HTML根元素


> While em is relative to the font-size of its direct or nearest parent, rem is only relative to the html (root) font-size. => Jeremy Church

# px

# pt



# em
有一个比较普遍的误解，认为 em 单位是相对于父元素的字体大小。 事实上，根据W3标准 ，它们是相对于使用em单位的元素的字体大小或者最近的父元素的字体大小。

### 利
* 解决了浏览器放大或缩小，页面布局乱的问题

### 弊
* 可读性不好，对看到的值会有不确定性
因为em是相对于父元素来计算的，比如看到1.4em，我们需要知道父元素的具体值

# rem
> font size of the root element” 

### 利
* 浏览器缩放后，显示正常
* 只要知道了根元素的大小，我们就知道了当前元素的大小


# 资料
[Confused About REM and EM?](https://j.eremy.net/confused-about-rem-and-em/)

[综合指南: 何时使用 Em 与 Rem](http://webdesign.tutsplus.com/zh-hans/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984)

[CSS3的REM设置字体大小](http://www.w3cplus.com/css3/define-font-size-with-css3-rem)

[CSS Font-Size: em vs. px vs. pt vs. percent](http://kyleschaeffer.com/development/css-font-size-em-vs-px-vs-pt-vs/)

http://www.cnblogs.com/leejersey/p/3662612.html
