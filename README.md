# toggleAnimate
- 基于Animate.css、zepto.js/jQoery的css动画切换组件。

- [https://issaxite.github.io/lib/toggleAnimate/](https://issaxite.github.io/lib/toggleAnimate/)

# 目的
- 解决两个不同Animate.css的连贯使用；
- 解决使用一个html组件实现数据切换；
- 解决两个Animate切换过慢的问题（Animate.css动画默认是1000ms完成）。

# 例子
**1.最简单例子**
  
- 使用参数模式
```js
var animateClass = "bounceInRight";
$.fn.toggleAnimate(animateClass);

$.fn.toggleAnimate(animateClass, function(){
  console.log('i am callback');
});
```
- 使用对象模式
```js
var animateClass = "bounceInRight";
$.fn.toggleAnimate({
  enterClass: 'bounceInRight'
});

$.fn.toggleAnimate({
  enterClass: 'bounceInRight',
  toggleCallback: function(){
    console.log('i am callback');
  }
});
*以上两种模式实现的效果是一样的*
```
**2.复杂的例子**
```js
var enterClass = "bounceOutRight",
    leaveClass = "bounceInLeft";
var enterDeley = '0.5s',  //0.5 or 500 or 500ms
    leaveDelay = '0.5';

$.fn.toggleAnimate({
  enterDelay: enterDelay,               // [可选] 首个动画的执行时间
  leaveDelay: leaveDelay,               // [可选] 第二个动画的执行时间
  enterClass: enterClass,               // [必选] 首个动画类名
  leaveClass: leaveClass,               // [可选] 第二个动画类名
  enterCallback: function(){            // [可选] 首个动画执行前回调
    console.log('i am enterCallback');
  },
  toggleCallback: function(){           // [可选] 在首个动画完成与第二个动画开始前之间回调
    console.log('i am toggleCallback');
  },
  leaveCallback: function(){            // [可选] 第二个动画完成后回调
    console.log('i am leaveCallback');
  }
});
```

# 使用场景
- 在编写轮播组件的时候，一般有多个轮播item。但是，使用该(小小)库，可以只是用item，然后在首个动画完成时（消失的时候），使用ViewModel对改item进行数据更新。

