TOPICS: <figcaption>
        <figure>
AUTHORS: Wizard; wizardforcel@mozilla.net; mdn:wizardforcel
         Crystal-RainSlide; Crystal-RainSlide@github.com; github:Crystal-RainSlide

# `<figcaption>`

**HTML `<figcaption>` 元素** 是与其相关联的图片的说明/标题，用?于描述其父节点 `<figure>` 元素里的其他数据。这意味着 `<figcaption>` 在
`<figure>` 块里是第一个或最后一个。同时 HTML Figcaption 元素是可选的；如果没有该元素，这个父节点的图片只是会没有说明/标题。

|  |  |
| :-- | :-- |
| **内容分类** | 无 |
| **允许的内容** | 流式内容 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | `<figure>` 元素；`<figcaption>` 元素必须是它的第一个或者最后一个子节点。|
| **DOM 接口** | `HTMLElement` |

## 属性

仅仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)

## `<figure>`

HTML `<figure>` 元素代表一段独立的内容, 经常与说明（caption） `<figcaption>` 配合使用, 并且作为一个独立的引用单元。当它属于主内容流（main flow）时，它的位置独立于主体。这个标签经常是在主文中引用的图片，插图，表格，代码段等等，当这部分转移到附录中或者其他页面时不会影响到主体。

|  |  |
| :-- | :-- |
| **内容分类** | 流内容，切片根，可触知的内容。|
| **允许的内容** | 一个`<figcaption>`元素，后跟流程内容； 或流内容后跟一个`<figcaption>`元素； 或流内容。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 所有接受流量内容的元素 |
| **允许的 ARIA 角色** | `group`, `presentation` |
| **DOM 实例** | `HTMLElement` |

### 使用说明

- 通常，`<figure>`是图像，插图，图表，代码片段等，在文档的主流程中引用，但可以移动到文档的另一部分或附录而不影响主流程。
- 作为sectioning root，`<figure>`元素的内容轮廓将从文档的主要轮廓中排除。
- 通过在其中插入`<figcaption>`（作为第一个或最后一个子元素），可以将标题与`<figure>`元素相关联。图中找到的第一个`<figcaption>`元素显示为图的标题。

## 示例

### 图像

```html
<!-- Just an image -->
<figure>
  <img
  src="https://developer.cdn.mozilla.net/media/img/mdn-logo-sm.png"
  alt="A robotic monster over the letters MDN.">
</figure>

<!-- Image with a caption -->
<figure>
  <img
  src="https://developer.cdn.mozilla.net/media/img/mdn-logo-sm.png"
  alt="A robotic monster over the letters MDN.">
  <figcaption>MDN Logo</figcaption>
</figure>
```

### 代码段

```html
<figure>
  <figcaption>Get browser details using <code>navigator</code>.</figcaption>
  <pre>
function NavigatorExample() {
  var txt;
  txt = "Browser CodeName: " + navigator.appCodeName;
  txt+= "Browser Name: " + navigator.appName;
  txt+= "Browser Version: " + navigator.appVersion ;
  txt+= "Cookies Enabled: " + navigator.cookieEnabled;
  txt+= "Platform: " + navigator.platform;
  txt+= "User-agent header: " + navigator.userAgent;
}</pre>
</figure>
```

### 引用内容

```html
<figure>
  <figcaption><cite>Edsger Dijkstra:</cite></figcaption>
  <blockquote>If debugging is the process of removing software bugs,
  then programming must be the process of putting them in.</blockquote>
</figure>
```

### 诗歌

```html
<figure>
  <p style="white-space: pre;">
Bid me discourse, I will enchant thine ear,
  Or like a fairy trip upon the green,
Or, like a nymph, with long dishevell'd hair,
  Dance on the sands, and yet no footing seen:
Love is a spirit all compact of fire,
  Not gross to sink, but light, and will aspire.</p>
  <figcaption><cite>Venus and Adonis</cite>,
    by William Shakespeare</figcaption>
</figure>
```
