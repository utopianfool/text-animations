# Cascading Text Animation

This cascading/floating text animation is applied to the body element and create a div and spans as it runs. [Demo](http://phil.devnation.co.uk/text-animations/cascade.php)

## CSS

```
/* floating text animation =====================================*/
.animation-container {
  position: fixed;
  top: 320px;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
}

.animation-container span {
  color: black;
  display: block;
  font-size: 18px;
  font-family: 'Helvetica';
  text-shadow: 0 0 1px grey;
  position: absolute;
  user-select: none;
  pointer-events: none;
  cursor: default;
  z-index: 1;
  opacity: 0;
  will-change: transform, opacity;
  animation-timing-function: ease-out;
  animation-name: move;
}

@keyframes move {
  0% {
    opacity: 0;
    transform: translateY(100vh);
  }
  25% {
    opacity: 1;
  }
  50% {
    opacity: 1;
  }
  75% {
    opacity: 0;
  }
  100% {
    opacity: 0;
    transform: none;
  }
}
```

## Javascript

```
// floating text

    'use strict';

var app = {

  chars: ['hello','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z','0','1','2','3','4','5','6','7','8','9'],

  init: function () {
    app.container = document.createElement('div');
    app.container.className = 'animation-container';
    document.body.appendChild(app.container);
    window.setInterval(app.add, 100);
  },

  add: function () {
    var element = document.createElement('span');
    app.container.appendChild(element);
    app.animate(element);
  },

  animate: function (element) {
    var character = app.chars[Math.floor(Math.random() * app.chars.length)];
    var duration = Math.floor(Math.random() * 15) + 1;
    var offset = Math.floor(Math.random() * (100 - duration * 2)) + 3; // edit width 100 as percentage of screen size
    var size = 10 + (15 - duration); // var size edit 10 for text size
    element.style.cssText = 'right:'+offset+'vw; font-size:'+size+'px;animation-duration:'+duration+'s';
    element.innerHTML = character;
    window.setTimeout(app.remove, duration * 1000, element);
  },

  remove: function (element) {
    element.parentNode.removeChild(element);
  },

};

document.addEventListener('DOMContentLoaded', app.init);

```