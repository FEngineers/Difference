不同的单位有不同的利弊

我们需要知道在何时使用哪个单位合适


> While em is relative to the font-size of its direct or nearest parent, rem is only relative to the html (root) font-size. => Jeremy Church


# px
### 利
* 一致
* 比较稳定和精确

### 弊
* 当用户在浏览器中浏览我们制作的Web页面时，他改变了浏览器的字体大小，这时会使用我们的Web页面布局被打破

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