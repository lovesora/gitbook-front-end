> How

# 添加CSS3的Animation
```js
    let styleSheet = document.styleSheets[0];

    let animationRotate = `animationRotate`;

    let keyframes =`@-webkit-keyframes animationRotate {
        from {-webkit-transform:rotate(0deg);} 
        to {-webkit-transform:rotate(360deg);}
    }`;

    styleSheet.insertRule(keyframes, styleSheet.cssRules.length);

    document.querySelector('.className').style.animation = 'animationRotate 5s linear 2s infinite alternate';
```