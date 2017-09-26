# basis
```scss
// scss
@mixin txt-container(/*默认参数*/$txt-color: #fff) {
    display: block;
    // 支持子选择器
    .txt {
        color: $txt-color;
    }
    // 支持选择父选择器
    &__addon {
        padding: 15px;
    }
}
// 使用mixin
.deault-container {
    @include txt-container();
}
```
被编译为
```css
.deault-container {
    display: block;
}

.deault-container .txt {
    color: #fff;
}

.deault-container__addon {
    padding: 15px;
}
```

# 在mixin中使用mixin
```scss
@mixin black-container($font-size: 2vw) {
    font-size: $font-size;
    @include txt-container(#000);
}
.black-container {
    @include black-container(1vw);
}
```
被编译为
```css
.black-container {
    font-size: 1vw;
    display: block;
}

.black-container .txt {
    color: #000;
}

.black-container__addon {
    padding: 15px;
}
```

# 剩余参数
```scss
@mixin rest-args($shadows...) {
    -moz-box-shadow: $shadows;
    -webkit-box-shadow: $shadows;
    box-shadow: $shadows;
}
.shadows {
    $shadows: 0px 4px 5px #666, 2px 6px 10px #999;
    @include rest-args(/*使用剩余参数作为参数，与es6在使用上有区别*/$shadows...);
}
```
被编译为
```css
.shadows {
    -moz-box-shadow: 0px 4px 5px #666, 2px 6px 10px #999;
    -webkit-box-shadow: 0px 4px 5px #666, 2px 6px 10px #999;
    box-shadow: 0px 4px 5px #666, 2px 6px 10px #999;
}
```

# @content用法
```scss
@mixin content-usage($color) {
    .txt {
        color: $color;
        @content;
    }
}
@include content-usage(red) {
    .fz {
        font-size: 15px;
    }
}
```
被编译为
```css
.txt {
    color: red;
}

.txt .fz {
    font-size: 15px;
}
```