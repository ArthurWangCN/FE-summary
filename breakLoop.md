## 跳出循环

### for跳出循环

使用break：

```js
function getItemById(arr, id) {
        var item = null;
        for (var i = 0; i < arr.length; i++) {
            if (arr[i].id == id) {
                item = arr[i];
                break;
            }
        }
        return item;
    }
```



### jquery 跳出循环

return false:

```

```





### forEach循环：

说明：

+ forEach()无法在所有元素都传递给调用的函数之前终止遍历，
+ return false 在这里起的作用是：只是终止本次继续执行，而不是终止for循环。

正确做法：

　　因为forEach()无法通过正常流程终止，所以可以通过抛出异常的方式实现终止



```js
function getItemById(arr, id) {
        var item = null;
        try {
            arr.forEach(function (curItem, i) {
                if (curItem.id == id) {
                    item = curItem;
                    throw Error();
                }
            })
        } catch (e) {
        }
        return item;
    }
```





3.1 foreach()不能使用break和continue这两个关键字，foreach和普通的for循环是不同的，它不是普通的遍历，实现continue的效果可以直接使用return。

3.2 forEach的优势一个是它的回调函数形成了一个作用域，它的curItem和i不会像for循环一样污染全局变量，再一个是更容易写出来函数式的代码，和map、filter、reduce这些高阶函数是一脉相承的。

3.3 forEach()本身无法跳出循环，必须遍历所有的数据才能结束。参考链接：https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach





### js里return和return false 的区别

1、都可以终止执行当前方法；

2、如果方法A调用了方法B，则在方法A中使用return可以终止程序，
但是在方法B中使用return则终止执行B方法，A方法继续执行，
这个时候需要在方法B中return false,方法A根据B方法的返回boolean值
决定是否终止A方法即可；

如下：

B: function(form){ //方法B

var cycleKindRadio = form.down('radiogroup[name=cycleKindRadio]');
var contentKindRadio = form.down('radiogroup[name=contentKindRadio]');

if(Ext.isEmpty(cycleKindRadio.getValue().cycleKind) || cycleKindRadio.getValue().cycleKind == ''){
Alert.Error('请选择时间！');
return false;
}
if(Ext.isEmpty(cycleKindRadio.getValue().contentKind) || contentKindRadio.getValue().contentKind == ''){
Alert.Error('请选择内容！');
return false;
}

return true;
},


A: function(btn){ //方法A
var _this = this;
var win = btn.up("window");
var form = win.down('form');

if(!_this.checkEmpty(form)) return;//根据B的返回结果决定是否执行

form.getForm().submit({//以上不终止，则该方法继续执行