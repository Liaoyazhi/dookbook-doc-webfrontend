TOPICS: border-spacing property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `border-spacing`

**`border-spacing`** 属性指定相邻单元格边框之间的距离（只适用于 边框分离模式 ）。相当于 HTML 中的 `cellspacing` 属性，但是第二个可选的值可以用来设置不同于水平间距的垂直间距。

`border-spacing` 值也适用于表格的外层边框上，即表格的边框和第一行的、第一列的、最后一行的、最后一列的单元格之间的间距是由表格相应的（水平的或垂直的） 边框间距（`border-spacing`）和相应的（上，右，下或左）内边距之和。

该属性只适用于 `border-collapse` 值是 `separate` 的时候。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **length** | 描述单元格之间的水平和垂直距离的一个 length 值。它只在单值语法下使用 |
| **`horizontal`** | 描述相邻两列的单元格之间的水平距离的一个 length 值。它只在双值语法下使用 |
| **`vertical`** | 描述相邻两行的单元格之间的垂直距离的一个 length 值。它只在双值语法下使用 |
| **`inherit`** | 一个表示父元素的 border-spacing 的计算值的关键字，其父元素必须应用了 border-spacing |

## 示例

```css
table.ex1 {
  border-collapse:separate;
  border-spacing:10px;
}

table.ex2 {
  border-collapse:separate;
  border-spacing:10px 50px;
}
```

```html
<table class="ex1" border="1">
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
  <tr>
    <td>Lois</td>
    <td>Griffin</td>
  </tr>
</table>

<br>

<table class="ex2" border="1">
  <tr>
    <td>Cleveland</td>
    <td>Brown</td>
  </tr>
  <tr>
    <td>Glenn</td>
    <td>Quagmire</td>
  </tr>
</table>
```
