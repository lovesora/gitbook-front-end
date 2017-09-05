> How

# 每个route的切换效果
```js
<ReactCSSTransitionGroup
    transitionName="fadeWrapper"
    transitionEnterTimeout={ 500 }
    transitionLeaveTimeout={ 500 }
>
</ReactCSSTransitionGroup>
```

```css
.fadeWrapper-enter {
    opacity: 0;
}

.fadeWrapper-enter.fadeWrapper-enter-active {
    opacity: 1;
    transition: opacity 500ms ease-in;
}

.fadeWrapper-leave {
    opacity: 1 ;
    transition: opacity 300ms ease-in ;
}

.fadeWrapper-leave.fadeWrapper-leave-active {
    opacity: 0;
}

.fadeWrapper {
    position: relative;
}
```