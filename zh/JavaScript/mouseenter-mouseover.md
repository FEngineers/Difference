* 不论鼠标指针穿过被选元素或其子元素，都会触发 mouseover 事件。对应mouseout
* 只有在鼠标指针穿过被选元素时，才会触发 mouseenter 事件。对应mouseleave


mouseenter在domlevel3中才被定义，目前在chrome中不被原生支持，

但是各大框架的事件系统都摸了了mouseenter事件。

大多数情况下，mouseover和mouseenter产生的结果都差不多，那为什么还要搞一个mouseenter呢？

我认为，mouseover是逻辑关系上的事件，即一旦某dom元素的子元素被mouseover了，它自己也就被mouseover了，

而mouseenter却是物理上的，即只有你眼睛看到光标进入了的元素，才会触发mouseenter事件，mouseleave同理。

[mouseover与mouseenter的区别](http://www.cnblogs.com/libmw/articles/2600747.html)