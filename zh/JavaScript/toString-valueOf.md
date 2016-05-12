```
var colors = ["red", "blue", "green"]; // 创建一个包含3 个字符串的数组  
alert(colors.toString()); // red,blue,green  
alert(colors.valueOf()); // red,blue,green  
alert(colors); // red,blue,green  
```


### valueOf

JavaScript calls the valueOf method to convert an object to a primitive value. You rarely need to invoke the valueOf method yourself; JavaScript automatically invokes it when encountering an object where a primitive value is expected.

By default, the valueOf method is inherited by every object descended from Object. Every built-in core object overrides this method to return an appropriate value. If an object has no primitive value, valueOf returns the object itself.

You can use valueOf within your own code to convert a built-in object into a primitive value. When you create a custom object, you can override Object.prototype.valueOf() to call a custom method instead of the default Object method.


### toString

Every object has a toString() method that is automatically called when the object is to be represented as a text value or when an object is referred to in a manner in which a string is expected. By default, the toString() method is inherited by every object descended from Object. If this method is not overridden in a custom object, toString() returns "[object type]", where type is the object type. The following code illustrates this:
