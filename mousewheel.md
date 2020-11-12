# mousewheel事件

+ 当用户通过鼠标滚轮与页面交互、在垂直方向上滚动页面时，就会触发 **mousewheel** 事件，这个事件就是实现全屏切换效果需要用到的。
+ 在IE6, IE7, IE8, Opera 10+, Safari 5+中，都提供了 “mousewheel” 事件，而 Firefox 3.5+ 中提供了一个等同的事件：**DOMMouseScroll**。
+ 与mousewheel事件对应的event对象中我们还会用到另一个特殊属性 —— wheelDelta属性。

+ “mousewheel” 事件中的 “event.wheelDelta” 属性值：返回的值，如果是正值说明滚轮是向上滚动，如果是负值说明滚轮是向下滚动；返回的值，均为 120 的倍数，即：幅度大小 = 返回的值 / 120。
+ “DOMMouseScroll” 事件中的 “event.detail” 属性值：返回的值，如果是负值说明滚轮是向上滚动（与 “event.wheelDelta” 正好相反），如果是正值说明滚轮是向下滚动；返回的值，均为 3 的倍数，即：幅度大小 = 返回的值 / 3。
