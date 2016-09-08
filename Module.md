## exports 和 module.exports 差異
```js

// exports 指向module.exports 的參考
exports.hello = function() { // in app.js
  console.log('hello');
}
// 相當於
module.exports.hello = function() { // in app.js
  console.log('hello');
}

var func = require('./app.js'); // require 是 module.exports 而不是 exports
func.hello() // hello

// 注意 不要寫成這樣, 如此一來 exports 指向不是module.exports
exports = function() {
  console.log('hello'); 
}

// 除非這樣改寫
module.exports = function() {
  console.log('hello');
}
exports = module.exports; // 確保exports


// 也可以這樣寫
exports = module.exports = function() {
  console.log('hello');
}

```



## 參考資料
[exports 和 module.exports 差異](https://cnodejs.org/topic/5231a630101e574521e45ef8)