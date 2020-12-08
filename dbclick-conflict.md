## 解决鼠标单击、双击事件冲突问题
### 问题描述
如果想让一个 DOM 对象既可以被单击，也可以被双击，可以在该对象上同时绑定单击（click）和双击（dblclick）事件。

```js
box.onclick = function() {
  console.log('click');
}
box.ondblclick = function() {
  console.log('dbclick');
}
```

此时会打印两次click，一次dbclick，这显然不是想要的结果。


### 解决办法
通过设置两次点击事件的间隔时间(setTimeout 方法)，来实现双击、单击事件并存。
+ 单击后不立刻执行相关的代码，而是让其延时执行（比如：200ms）
+ 如果随后发生了双击事件，则取消延时执行的方法，只执行双击事件方法。

```js
var clickTimer;
box.onclick = function() {
  clearTimeout(clickTimer);
  clickTimer = setTimeout(function() {
    console.log('click');
  }, 200);
}
box.ondblclick = function() {
  clearTimeout(clickTimer);
  console.log('dbclick');
}
```


