# toggleAnimate
基于Animate.css、zepto.js/jQoery的css动画切换组件。

# 目的
- 解决两个不同Animate.css的连贯使用；
- 解决使用一个html组件实现数据切换；
- 解决两个Animate切换过慢的问题（Animate.css动画默认是1000ms完成）。

# 例子
```
var $text = $("#animationSandbox"),
    $testBtn = $("#test")
    $enterClass = $("#enterClass select"),
    $leaveClass = $("#leaveClass select"),
    $delay = $("#delay select");

$testBtn.on('click', function(){
  var enterClass = "bounceOutLeft",
      leaveClass = "bounceInRight",
      delay = 300;  

  $text.toggleAnimate({
    delay: delay, // 两个动画切换的延时
    enterClass: enterClass, // 首个动画
    enterClassCallback: function(){
      // 首个动画完成时调用（1000ms后回调，延时由Animate.css的演示决定）
    },
    callback: function(){
      // 首个动画执行时回调
    },
    leaveClass: leaveClass, // 第二个动画
  });
});
```

