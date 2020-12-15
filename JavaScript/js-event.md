# JavaScript事件对象event



## 坐标相关

event 有关于当前触发元素的相关坐标，它们是：

- `pageX、pageY`
- `screenX、screenY`
- `clientX、clientY`
- `offsetX、offsetY`



简单来说：

1. `pageX、pageY`表示离文档页面的坐标，如果发生滚动，则要把滚动距离也算上。
2. `offsetX、offsetY`表示相对于事件源元素（精准触发元素）的坐标。
3. `screenX、screenY`表示相对屏幕的坐标。
4. `clientX、clientY`表示相对可视窗口的坐标。

下面以Google Chrome为例来图示说明：



### 关于X

![点击边缘](http://blogpic.at15cm.com/event-x-edge.png)

![点击内部](http://blogpic.at15cm.com/event-x-inside.png)

![带滚动](http://blogpic.at15cm.com/event-x-scroll.png)



### 关于Y

![点击边缘](http://blogpic.at15cm.com/event-y-edge.png)

![点击内部](http://blogpic.at15cm.com/event-y-inside.png)

![带滚动](http://blogpic.at15cm.com/event-y-scroll.png)



### 不同浏览器的支持

|         |       Chrome       |      Firefox       |       ie8 -        |        ie9         |       ie10 +       |
| :-----: | :----------------: | :----------------: | :----------------: | :----------------: | :----------------: |
| offsetX | :heavy_check_mark: |        :x:         | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| clientX | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
|  pageX  | :heavy_check_mark: | :heavy_check_mark: |        :x:         | :heavy_check_mark: | :heavy_check_mark: |
| screenX | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| layerX  | :heavy_check_mark: | :heavy_check_mark: |        :x:         | :heavy_check_mark: | :heavy_check_mark: |
|    x    | :heavy_check_mark: |        :x:         | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |



### 对于layerX和x

layerX、layerY 和 x、y 是实验中的功能，标准可能重新修订，所以不推荐使用。

+ layerX：

![layerX](http://blogpic.at15cm.com/event-layer.jpg)

+ x：

![x](http://blogpic.at15cm.com/event-xy.jpg)



原文：https://www.jianshu.com/p/f91599d64201?utm_campaign
