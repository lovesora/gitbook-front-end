> How

# Select
```html
<select ng-model="selected" ng-options="x.id as x.name for x in users"></select>
```

```js
$scope.users = [
    {name:'a',id:'1'},
    {name:'b',id:'2'},
    {name:'c',id:'3'}
];
$scope.selected='2';//id的值，区分类型
$scope.selected=$scope.users[0].id;//如果想要第一个值
```