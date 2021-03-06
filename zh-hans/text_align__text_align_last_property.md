TOPICS: text-align property
        text-align-last property

# CSS 属性: `text-align`、`text-align-last`

**`text-align`** CSS属性定义行内内容（例如文字）如何相对它的块父元素对齐。`text-align` 并不控制块元素自己的对齐，只控制它的行内内容的对齐。

 **`text-align-last`** CSS 属性描述的是一段文本中最后一行在被强制换行之前的对齐规则。

## `text-align` 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`left`** | 文本左对齐。默认值：由浏览器决定。|
| **`right`** | 文本右对齐。|
| **`center`** | 文本居中对齐。|
| **`justify`** | 文本两端对齐。|
| `inherit`| 规定应该从父元素继承 `text-align` 属性的值。|

## `text-align-last` 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`left`** | 最后一行向左对齐。|
| **`right`** | 最后一行向右对齐。|
| **`center`** | 最后一行居中对齐。|
| **`auto`** | 默认值。最后一行被调整，并向左对齐。|
| **`justify`** | 最后一行被调整为两端对齐。|
| **`start`** | 最后一行在行开头对齐（如果 `text-direction` 是从左到右，则向左对齐；如果 `text-direction` 是从右到左，则向右对齐）。|
| **`end`** | 最后一行在行末尾对齐（如果 `text-direction` 是从左到右，则向右对齐；如果 `text-direction` 是从右到左，则向左对齐）。|
| `inherit`| 规定应该从父元素继承 `text-align-last` 属性的值。|

!!! warn "`justify`"
    最后一个水平对齐属性是`justify`，它有时会出现一些问题。例：最后一行只有较少单词时，文本行的左右两端都会放在父元素的内边界上。会是的字符间距看上去太大。此时可以调整单词和字母间的间隔，使各行的长度恰好相等。

## 示例: `text-align`

```css
.example {
  text-align: left;
  border: solid;
}
```

```html
<p class="example">
  Integer elementum massa at nulla placerat varius.
  Suspendisse in libero risus, in interdum massa.
  Vestibulum ac leo vitae metus faucibus gravida ac in neque.
  Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p>
```

## 示例: `text-align-last`

```css
div {
  text-align: justify;
  text-align-last: right;
  -moz-text-align-last: right; /* 针对 Firefox 的代码 */
}
```

```html
<div>
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property. You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
You can use the text-align-last property to align the last line of a text, if the text has the text-align property set to justify. This text is where you will see the result of the  text-align-last property.
</div>
```
