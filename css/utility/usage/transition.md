# height为auto时的动画效果
```css
.panel {
    overflow: hidden;
    max-height: 100px;

    transition: max-height $timing-transition;
}

.panel--collapsed {
    max-height: 0;
}
```