# 判断是否使用了new关键字通过构造函数实例对象
```js
// solution 1
function People(name){
  'use strict';
  this._name = name;
}

// use strict命令保证了该函数在严格模式下运行。由于在严格模式中，函数内部的this不能指向全局对象，默认等于undefined，导致不加new调用会报错（JavaScript 不允许对undefined添加属性）
People()
// TypeError: Cannot set property '_foo' of undefined

// solution 2
function People(name) {
    if (!(this instanceof People))
        return new People(name);

    this._name = name;
}

let p = People('liuxin');
console.log(p._name);// liuxin

// solution 3
// 函数内部可以使用new.target属性。如果当前函数是new命令调用，new.target指向当前函数，否则为undefined。
function People(name) {
    if (new.target !== People)
        return new People(name);
    
    this._name = name;
}
let p = People('liuxin');
console.log(p._name);
```

# Resources
* [ruanyifeng](http://javascript.ruanyifeng.com/oop/basic.html)