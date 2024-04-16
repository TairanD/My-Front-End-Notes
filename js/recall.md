# Recall Function


## Example: map in Js
```js
function customMap(array, callback) {
  const result = [];

  for (let i = 0; i < array.length; i++) {
    result.push(callback(array[i], i, array));
  }

  return result;
}

// 示例使用
const numbers = [1, 2, 3, 4, 5];

// 使用自定义 map 函数将数组每个元素加倍
const doubledNumbers = customMap(numbers, number => {
  return number * 2;
});
```

## Why the beginner always feel confused in this part

在 JavaScript 中，当你创建一个回调函数作为实参传递给另一个函数时，回调函数中的参数通常是形参。
具体说，形参是指在函数声明或函数表达式中定义的参数，而实参是在调用函数时传递给函数的值。

```js
// 函数a接受一个回调函数作为参数
function a(callback) {
  // 在这里调用回调函数，并传递参数给它
  const data = "Hello from a";
  callback(data);
}

// 在调用a时，传递一个回调函数给它
a(b => {
  // 这里的b是回调函数的形参
  console.log(b); // 输出 "Hello from a"
});
```

js是一种解释性语言，它会在执行代码时逐行解释。因此，如果在使用函数之前尝试调用尚未定义的函数，可能会导致错误

- 由此，我们可知callback函数声明时传入的形式参数由它之上的实际参数决定，这个参数的值由它之上的将callback作为形式参数的函数内部决定
  - 某种程度上我们可以说 **_实际创建callback逻辑（定义函数内容）_** 时我们是受 **_未实际创建callback逻辑而直接调用的代码_** 决定的 - 
定义函数内容时参数的类型、数量受限制

- 而普通函数声明时传入的形式参数由它之下的实际参数决定，这个参数的值由它之下的调用普通函数时的声明决定
  - **_未实际创建callback逻辑而直接调用_** 时我们是受 **_实际创建普通函数逻辑的代码_** 决定的