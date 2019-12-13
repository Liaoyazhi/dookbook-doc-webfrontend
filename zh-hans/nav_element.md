TOPICS: <nav>
AUTHORS: ZoomZhao; zoom.zhao@gmail.com; github:ZoomZhao
         石博文; bowen-shi@mozilla.net; mdn:bowen-shi
         紫云飞; ziyunfei@mozilla.net; mdn:ziyunfei

# HTML导航元素: `<nav>`

**HTML `<nav>` 元素**表示页面的一部分，其目的是在当前文档或其他文档中提供**导航链接**。导航部分的常见示例是菜单，目录和索引。

|  |  |
| :-- | :-- |
| **内容分类** | `流式内容`, `区块内容`, 可视的内容. |
| **允许的内容** | `流式内容`. |
| **忽略的标记** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 所有允许`流式内容`的元素 |
| **允许的 ARIA 角色** | None |
| **DOM 接口** | `HTMLElement` |

## 属性

这个元素只包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

## 使用说明

- 并不是所有的链接都必须使用`<nav>`元素,它只用来将一些热门的链接放入导航栏,例如[`<footer>`](/zh-hans/webfrontend/<footer>)元素就常用来在页面底部包含一个不常用到,没必要加入`<nav>`的链接列表.
- 一个网页也可能含有多个`<nav>`元素,例如一个是网站内的导航列表,另一个是本页面内的导航列表.
- 对于屏幕阅读障碍的人,可以使用这个元素来确定是否忽略初始内容.

## 示例

```html
<nav>
  <ul>
    <li><a href="#">首页</a></li>
    <li><a href="#">关于</a></li>
    <li><a href="#">联系</a></li>
  </ul>
</nav>
```
