# 使用Controller as的好处：
### 解决嵌套$scope的问题

不使用Controller as, 如果出现嵌套时的作用域
```
<div ng-controller="MainCtrl">
  {{ title }}
  <div ng-controller="AnotherCtrl">
    {{ title }}
    <div ng-controller="YetAnotherCtrl">
      {{ title }}
    </div>
  </div>
</div>
```

如果使用了Controller as
```
<div ng-controller="MainCtrl as main">
  {{ main.title }}
  <div ng-controller="AnotherCtrl as another">
    {{ another.title }}
    <div ng-controller="YetAnotherCtrl as yet">
      {{ yet.title }}
    </div>
  </div>
</div>
```

Controller as的好处一目了然

而且，在不使用Controller as时，如果想要访问父级的作用域，我们可能这样写
```
<div ng-controller="MainCtrl">
  {{ title }}
  <div ng-controller="AnotherCtrl">
    Scope title: {{ title }}
    Parent title: {{ $parent.title }}
    <div ng-controller="YetAnotherCtrl">
      {{ title }}
      Parent title: {{ $parent.title }}
      Parent parent title: {{ $parent.$parent.title }}
    </div>
  </div>
</div>
```
使用了Controller as以后，代码看起来会更好理解
```
<div ng-controller="MainCtrl as main">
  {{ main.title }}
  <div ng-controller="AnotherCtrl as another">
    Scope title: {{ another.title }}
    Parent title: {{ main.title }}
    <div ng-controller="YetAnotherCtrl as yet">
      Scope title: {{ yet.title }}
      Parent title: {{ another.title }}
      Parent parent title: {{ main.title }}
    </div>
  </div>
</div>
```

# 使用Controller as不好的地方
### 当我们想使用$watchers的时候
```
app.controller('MainCtrl', function ($scope) {
  this.title = 'Some title';
  // doesn't work!
  $scope.$watch('title', function (newVal, oldVal) {});
  // doesn't work!
  $scope.$watch('this.title', function (newVal, oldVal) {});
});
```
实际上，我们需要这样写才行
```
app.controller('MainCtrl', function ($scope) {
  this.title = 'Some title';
  // boom
  $scope.$watch(angular.bind(this, function () {
    return this.title; // `this` IS the `this` above!!
  }), function (newVal, oldVal) {
    // now we will pickup changes to newVal and oldVal
  });
});
```


# 资料
[Digging into Angular’s “Controller as” syntax](https://toddmotto.com/digging-into-angulars-controller-as-syntax/)

[用$scope还是用controller as](http://pinkyjie.com/2015/02/09/controller-as-vs-scope/)

[Exploring Angular’s “Controller as” Syntax and the vm Variable](http://www.infragistics.com/community/blogs/dhananjay_kumar/archive/2015/07/02/exploring-angular-s-controller-as-syntax-and-the-vm-variable.aspx)