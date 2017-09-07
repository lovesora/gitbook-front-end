# 左侧固定，右侧自适应
```css
    .left: {
        float: left;
        width: 100px;
    }
    .right: {
        margin-left: 100px;
    }
```

# 右侧固定垂直居中，左侧自适应
```css
    .container: {
        display: table;
    }
    .left: {
        display: table-cell;
    }
    .right: {
        display: table-cell;
        vertical-align: middle;
        width: 100px;
    }
```