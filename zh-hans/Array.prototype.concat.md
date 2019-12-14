TOPICS: Array.prototype.concat
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Array.prototype.concat()`

`concat()` 方法用于合并两个或多个数组。此方法不会更改现有数组，而是返回一个新数组。

## 语法

```html
var new_array = old_array.concat(value1[, value2[, ...[, valueN]]])
```

| 参数 | 说明 |
| :-- | :-- |
| `valueN` | 将数组和/或值连接成新数组。如果省略了valueN参数参数，则concat会返回一个它所调用的已存在的数组的浅拷贝。详情请参阅下文描述。 |

**返回类型**：Array

## 描述

`concat`方法创建一个新的数组，它由被调用的对象中的元素组成，每个参数的顺序依次是该参数的元素（如果参数是数组）或参数本身（如果参数不是数组）。它不会递归到嵌套数组参数中。

`concat`方法不会改变`this`或任何作为参数提供的数组，而是返回一个浅拷贝，它包含与原始数组相结合的相同元素的副本。 原始数组的元素将复制到新数组中，如下所示：

- 对象引用（而不是实际对象）：`concat`将对象引用复制到新数组中。 原始数组和新数组都引用相同的对象。 也就是说，如果引用的对象被修改，则更改对于新数组和原始数组都是可见的。 这包括也是数组的数组参数的元素。
- 数据类型如字符串，数字和布尔（不是[`String`](/zh-hans/webfrontend/String_Object)，
[`Number`](/zh-hans/webfrontend/Number_Object) 和 [`Boolean`](/zh-hans/webfrontend/Boolean_Object) 对象）：`concat`将字符串和数字的值复制到新数组中。

!!! warn ""
    注意：数组/值在连接时保持不变。此外，对于新数组的任何操作（仅当元素不是对象引用时）都不会对原始数组产生影响，反之亦然。

## 示例

## 连接两个数组

以下代码将两个数组合并为一个新数组：

```javascript
var alpha = ['a', 'b', 'c'];
var numeric = [1, 2, 3];

alpha.concat(numeric);
// result in ['a', 'b', 'c', 1, 2, 3]
```

## 连接三个数组

以下代码将三个数组合并为一个新数组:

```javascript
var num1 = [1, 2, 3],
    num2 = [4, 5, 6],
    num3 = [7, 8, 9];

var nums = num1.concat(num2, num3);

console.log(nums);
// results in [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

## 将值连接到数组

以下代码将三个值连接到数组：

```javascript
var alpha = ['a', 'b', 'c'];

var alphaNumeric = alpha.concat(1, [2, 3]);

console.log(alphaNumeric);
// results in ['a', 'b', 'c', 1, 2, 3]
```

## 合并嵌套数组

以下代码合并数组并保留引用：

```javascript
var num1 = [[1]];
var num2 = [2, [3]];
var num3=[5,[6]];

var nums = num1.concat(num2);

console.log(nums);
// results is [[1], 2, [3]]

var nums2=num1.concat(4,num3);

console.log(nums2)
// results is [[1], 4, 5,[6]]

// modify the first element of num1
num1[0].push(4);

console.log(nums);
// results is [[1, 4], 2, [3]]
```
