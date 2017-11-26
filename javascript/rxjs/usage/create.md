# 创建

## empty、startWith

```js
var result = Rx.Observable.empty().startWith(7);
result.subscribe(x => console.log(x));
```

## create

```js
var observable = Rx.Observable.create(function (observer) {
  observer.next(1);
  observer.next(2);
  observer.next(3);
  observer.complete();
});
observable.subscribe(
  value => console.log(value),
  err => {},
  () => console.log('this is the end')
);
```

## of

```js
var numbers = Rx.Observable.of(10, 20, 30);
var letters = Rx.Observable.of('a', 'b', 'c');
var interval = Rx.Observable.interval(1000);
var result = numbers.concat(letters).concat(interval);
result.subscribe(x => console.log(x));
```

## from

```js
var array = [10, 20, 30];
var result = Rx.Observable.from(array);
result.subscribe(x => console.log(x));
```

## fromEvent

```js
var clicks = Rx.Observable.fromEvent(document, 'click');
clicks.subscribe(x => console.log(x));
```

## fromPromise

```js
var result = Rx.Observable.fromPromise(fetch('http://myserver.com/'));
result.subscribe(x => console.log(x), e => console.error(e));
```

## repeat

```js
Rx.Observable.from([1, 2]).repeat(2).subscribe(data => console.log(data))
```

## repeatWhen

```js
Rx.Observable.from([1, 2])
    .repeatWhen(() => Rx.Observable.timer(1000, 2000))
    .subscribe(data => console.log(data))
```

## range

```js
var numbers = Rx.Observable.range(1, 10)
    .reduce((b, a) => {console.log('b: ', b, 'a: ', a); return b + a;}, 0);
numbers.subscribe(x => console.log(x));
VM314:1 b:  0 a:  1
VM314:1 b:  1 a:  2
VM314:1 b:  3 a:  3
VM314:1 b:  6 a:  4
VM314:1 b:  10 a:  5
VM314:1 b:  15 a:  6
VM314:1 b:  21 a:  7
VM314:1 b:  28 a:  8
VM314:1 b:  36 a:  9
VM314:1 b:  45 a:  10
VM314:2 55
```

## timer

```js
var numbers = Rx.Observable.timer(3000, 1000);
numbers.subscribe(x => console.log(x));
```

## interval

```js
var numbers = Rx.Observable.interval(1000);
numbers.subscribe(x => console.log(x));
```



