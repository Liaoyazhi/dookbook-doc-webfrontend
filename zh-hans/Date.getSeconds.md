TOPICS: Date.getSeconds
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Date.getSeconds()`

**`getSeconds()`** 方法根据本地时间，返回一个指定的日期对象的秒数。

## 语法

```javascript
dateObj.getSeconds()
```

**参数**: 没有参数

**返回值**: Number

## 描述

该方法返回一个 `0` 到 `59` 的整数值。

## 示例

### 使用`getSeconds`方法

下面第二条语句，基于日期对象 `Xmas95` 的值，把 `30` 赋值给变量 `secs`。

```javascript
var Xmas95 = new Date("December 25, 1995 23:15:30");
var secs = Xmas95.getSeconds();
```
