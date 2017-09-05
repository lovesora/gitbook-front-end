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

# Event
```js
document.getElementById('rotaryContainer').addEventListener('webkitAnimationEnd', this.eventListener.bind(this));
document.getElementById('rotaryContainer').addEventListener('animationend', this.eventListener.bind(this));
```

# Resouces
* [CSS3动画](http://coderlt.coding.me/2017/06/09/animtion-css-base/)
