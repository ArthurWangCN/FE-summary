## 七种垂直居中的方法

- 设定行高（line-height）
- 添加伪元素
- calc动态计算
- 使用表格或假装表格
- transform
- 绝对定位
- 使用Flexbox



### 设定行高（line-height）

+ 设定行高是垂直居中最简单的方式，适用于“单行”的“行内元素”（inline、inline-block）；

+ 将line-height设成和高度一样的数值，则内容的行内元素就会被垂直居中，因为是行高，所以会在行内元素的上下都加上行高的1/2，所以就垂直居中了！



### 添加伪元素（::before、::after）

+ vertical-align属性虽然是垂直居中，不过却是指在元素内的所有元素垂直位置互相居中，并不是相对于外框的高度垂直居中。如果有一个方块变成了高度100%，那么其他的方块就会真正的垂直居中。
+ 利用::before和::after添加div进到杠杠内，让这个“伪”div的高度100%，就可以轻松地让其他的div都居中。div记得要把display设为inline-block，毕竟vertical-align:middle；是针对行内元素。

```css
.div0::before{
  content:'';
  width:0;
  height:100%;
  display:inline-block;
  position:relative;
  vertical-align:middle;
  background:#f00;
}
```





### calc动态计算



### 使用表格或假装表格

将要垂直居中元素的父元素的display改为table-cell。



### transform

+ translateY（改变垂直的位移，如果使用百分比为单位，则是以元素本身的长宽为基准） + top + position: relative;

```css
.use-transform{
    width:200px;
    height:200px;
    border:1px solid #000;
}
.use-transform div{
    position: relative;
    width:100px;
    height:50px;
    top:50%;
    transform:translateY(-50%);
    background:#095;
}
```





### 绝对定位

+ 将上下左右的数值都设为0，再搭配一个margin:auto
+ 注意：绝对定位的元素是会互相覆盖的





### 使用Flexbox

使用align-items或align-content的属性

