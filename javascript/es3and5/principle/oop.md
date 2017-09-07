# 什么是JS OOP
> 对象是单个实物的抽象。

> 对象是一个容器，封装了属性（property）和方法（method）

# 构造函数
```js
let People = function(name) {
	this.name = name;
}

let people = new People('liuxin');

console.log(people.name);//liuxin
```

如果不使用`new`直接调用构造函数，则会将构造函数当作普通函数执行

```js
let name = 'window';

let People = function(name) {
	this.name = name;
}

let newP = new People('liuxin');
let p = People('lx');// this指向window

console.log(newP.name);// liuxin
try {
	console.log(p.name);
} catch (e) {
	console.log(e);// TypeError: Cannot read property 'name' of undefined
}
console.log(name)// lx
```

使用Object.create()创建对象
```js
let people = {
    _name: 'liuxin',
    getName: function() {
        return this._name;
    }
}

let p = Object.create(people);
console.log(p.getName());// liuxin
```

# new 命令的原理
> 1. 创建一个空对象，作为将要返回的对象实例
> 2. 将这个空对象的原型，指向构造函数的prototype属性
> 3. 将这个空对象赋值给函数内部的this关键字
> 4. 开始执行构造函数内部的代码

以下是阮一峰老师的代码
```js
function _new(/* 构造函数 */ constructor, /* 构造函数参数 */ param1) {
  // 将 arguments 对象转为数组
  var args = [].slice.call(arguments);
  // 取出构造函数
  var constructor = args.shift();
  // 创建一个空对象，继承构造函数的 prototype 属性
  var context = Object.create(constructor.prototype);
  // 执行构造函数
  var result = constructor.apply(context, args);
  // 如果返回结果是对象，就直接返回，则返回 context 对象
  return (typeof result === 'object' && result != null) ? result : context;
}
```

# Resources
* [ruanyifeng](http://javascript.ruanyifeng.com/oop/basic.html)