### findAndReplace

在字符串中查找给定的单词，并替换为另一个单词

```js
const findAndReplace = (string, wordToFind, wordToReplace) => {
    string.split(wordToFind).join(wordToReplace);
}
let result = findAndReplace('banana I like banana', 'banana', 'apple');// "apple I like apple"
```



### RGBToHex

将RGB模式下的颜色转换为十六进制

```js
const RGBToHex = (r, g, b) => ((r << 16) + (g << 8) + b).toString(16).padStart(6, '0');
let hex = RGBToHex(255, 255, 255);//ffffff
```



### 