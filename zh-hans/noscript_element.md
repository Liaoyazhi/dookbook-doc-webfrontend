TOPICS: <noscript>

# `<noscript>`

如果页面上的脚本类型不受支持或者当前在浏览器中关闭了脚本，则在 **HTML `<noscript>` 元素**中定义脚本未被执行时的替代内容。

|  |  |
| :-- | :-- |
| **内容分类** | 元数据内容，流内容，短语内容. |
| **允许的内容** | 当脚本被禁用并且它是 [`<head>`](/zh-hans/webfrontend/<head>)元素的后代时：以下顺序任意，零个或者多个[`<link>`](/zh-hans/webfrontend/<link>)元素，零个或者多个&lt;style&gt;元素，零个或者多个[`<meta>`](/zh-hans/webfrontend/<meta>)元素。<br>当脚本被禁用并且它不是 [`<head>`](/zh-hans/webfrontend/<head>) 元素的子元素时：任何transparent content 都可以，但是在它的后代中必须没有 `<noscript>`元素。<br>否则：`flow content` 或 `phrasing content` 。|
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 如果没有根元素 `<noscript>`，或者在[`<head>`](/zh-hans/webfrontend/<head>)元素中（仅用于HTML文档）也没有根元素 `<noscript>`，允许任何 phrasing content 元素。|
| **DOM接口** | `HTMLElement` |

## 属性

该元素只包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

## 示例

```html
<noscript>
  <!-- anchor linking to external file -->
  <a href="http://www.mozilla.com/">External Link</a>
</noscript>
<p>Rocks!</p>
```
