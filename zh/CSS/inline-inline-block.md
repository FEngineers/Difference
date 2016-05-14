inline和inline-block都是css display的属性值，除此之外，还有些其他的值。

可以系统的学一下display的属性

```
display: none;

display: inline;
display: block;
display: inline-block;
display: contents;
display: list-item;
display: inline-list-item;
display: table;
display: inline-table;
display: table-cell;
display: table-column;
display: table-column-group;
display: table-footer-group;
display: table-header-group;
display: table-row;
display: table-row-group;
display: table-caption;
display: flex;
display: inline-flex;
display: grid;
display: inline-grid;
display: ruby;
display: ruby-base;
display: ruby-text;
display: ruby-base-container;
display: ruby-text-container;
display: run-in;

/* Global values */
display: inherit;
display: initial;
display: unset;
```


# display: inline
inline元素的特点是：
* 和其他元素都在一行上
* 高，行高及顶和底边距不可改变
* 宽度就是它的文字或图片的宽度，不可改变
```
<span>, <a>, <label>, <input>, <img>, <strong> 和<em>是inline元素的例子。
```

# display: inline-block
周围元素保持在同一行，但可以设置宽度和高度的块元素的属性

