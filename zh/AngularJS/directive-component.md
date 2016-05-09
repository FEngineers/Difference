directive有点component的感觉，但是在angular里面也有专门的.component方法，
他们的区别是什么？
什么时候该用哪个方法？

而且，component的定义方法好像和directive也比较相识

### 使用Components的好处

### 什么时候不该使用Component
directive有依赖于DOM操作，有个DOM添加事件坚挺
当一个directive是由属性或者css的class来触发的，而不是被element触发的

### 从directive转向component
```
// before
module.directive(name, fn);

// after
module.component(name, options);
```

细节：
* Function to Object, method name change
* “scope” and “bindToController”, to “bindings”
* Controller and controllerAs changes


### 资料
[Refactoring Angular Apps to Component Style](http://teropa.info/blog/2015/10/18/refactoring-angular-apps-to-components.html)

[Understanding Components](https://docs.angularjs.org/guide/component)

[Exploring the Angular 1.5 .component() method](https://toddmotto.com/exploring-the-angular-1-5-component-method/)

[Angular component() method back-ported to 1.3+](https://toddmotto.com/angular-component-method-back-ported-to-1.3/)

https://www.airpair.com/angularjs/posts/component-based-angularjs-directives