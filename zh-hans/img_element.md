TOPICS: <img>
        <img> src attribute
        <img> alt attribute
        <img> width attribute
        <img> height attribute
        <img> srcset attribute
        <img> sizes attribute
        <img> longdesc attribute
        <img> usemap attribute

# HTML 图像元素：`<img>`

**HTML `<img>` 元素** 代表文档中的一个**图像**。它是一个*可替换*的元素。

!!! warn "提示"
    从技术上讲，图像并不会插入HTML页面中，而是链接到HTML页面上。`<img>` 标签的作用是为被引用的图像创建占位符。
    通过在[`<a>`](/zh-hans/webfrontend/<a>)标签中嵌套`<img>`标签，给图像添加到另一个文档的链接。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | *流式内容*，*短语内容*，*嵌入内容*，*可触摸内容*。如果元素有 *[`usemap`](/zh-hans/webfrontend/<map>)*属性，它也是*交互内容*的一部分。|
| **允许的内容** | 无，它是一个 **[空元素](/zh-hans/webfrontend/empty_element)**。|
| **标签省略** | 必须有一个开始标签，不允许有结束标签。|
| **允许的父元素** | *嵌入内容*的任意元素。|
| **DOM 接口** | **`HTMLImageElement`** |

## 属性

这个元素包括 [HTML全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`src`** | (**必需的**) 图像URL地址。|
| **`alt`** | 描述图像的**替换文本**。如果图像地址是错误的、图像格式不支持、或者图像还没有被下载，用户将会看到这个显示。|
| **`width`** | 图像的**宽度** (单位是*像素*)。|
| **`height`** | 图像的**高度** (单位是*像素*)。|
| **`srcset`** | 以*逗号分隔*的字符串来指定**用户代理（即浏览器）可能使用的图像备选项**。|
| **`sizes`** | 以*逗号分隔*的字符串来表示**资源大小**。如果没有设置`srcset`属性，或者没值，那么`sizes`属性也将不起作用。|
| **`usemap`** | 与元素相关联的**图像映射**的URL（以`#`开始）。<br>使用说明：**如果 `<img>`元素是[`<a>`](/zh-hans/webfrontend/<a>)或[`<button>`](/zh-hans/webfrontend/<button>)元素的后代元素则不能使用这个属性。** 参考[`<map>`和`<area>`](/zh-hans/webfrontend/<map>)元素。|
| `crossorigin` | 这个枚举属性表明是否必须使用 CORS 完成相关图像的抓取。启用CORS的图像 在 [`<canvas>`](/zh-hans/webfrontend/<canvas>) 元素中可以重复使用而不会被污染。允许的值有：<br><br>`anonymous`<br>执行一个跨域的请求（比如，有 `Origin:` HTTP header）。但是没有发送证书（比如，没有 cookie，没有 X.509 证书，没有 HTTP 基本的授权认证）。如果服务器没有给源站证书（没有设置 Access-Control-Allow-Origin: HTTP头），图像会被污染而且它的使用会被限制。<br><br>`use-credentials`<br>一个有证书的跨域请求（比如，有 `Origin:` HTTP header）被发送 （比如，a cookie, a certificate, and HTTP Basic authenticationis performed）。如果服务器没有给源站发送证书（通过 Access-Control-Allow-Credentials: HTTP header），图像将会被污染，且它的使用会受限制。当用户并未显式使用本属性时，默认不使用 CORS 发起请求(例如，不会向服务器发送 HTTP 头部信息)，用以防止其在[`<canvas>`](/zh-hans/webfrontend/<canvas>)中的使用。如果无效，默认当做 **anonymous** 关键字生效。更多信息，请查看 CORS 属性设置 。 |
| `ismap` | 这个布尔属性表示图像是否是服务器端`map`的一部分。如果是，那么点击的精准坐标将会被发送到服务器。<br><br>**使用说明：** 只有在 `<img>` 元素是一个拥有有效 `href` 属性的 [`<a>`](/zh-hans/webfrontend/<a>) 元素的后代元素的情况下，这个属性才会被允许使用。 |

### 已废弃属性

| 属性 | 描述 |
| :-- | :-- |
| ~~`align`~~ |（**废弃**）图像相对于它周围上下文的对齐。使用 **`float`和/或`vertical-align`** 这两个CSS属性作为代替。|
| ~~`border`~~ |（**废弃**）图像周围的边框宽度。使用CSS属性 **`border`** 代替此废弃属性。|
| ~~`hspace`~~ |（**废弃**）插入到图像的左侧和右侧的空白像素的值。使用CSS属性`margin`代替此废弃属性。|
| ~~`longdesc`~~ |（**废弃**）一个指向更详细的图像描述的链接。可能的值是一个URL或一个页面上其他元素的`id`。<br> *备注：* 此属性在当前最新的W3C版本，HTML 5.2中被提到，但在WHATWG组织的 [HTML Living Standard](https://html.spec.whatwg.org/multipage/embedded-content.html#the-img-element) 中依然处于被移除的状态。它的未来尚无定数，应使用WAI-ARIA方法替代，例如: **`aria-by`或`aria-details`**。|
| ~~`name`~~ |（**废弃**）元素的名字。使用 **`id`** 属性代替此废弃属性。|
| ~~`vspace`~~ |（**废弃**）插入到图像的上方和下方的空白像素的数组。使用CSS属性 **`margin`** 代替此废弃属性。|

## 基础用法

!!! warn "**`alt`** 使用说明"
    浏览器并不总是显示该元素中的图像。对于非图形浏览器（包括那些有视力障碍的人所使用的）来说就是这种情况，如果用户选择不显示图像，或者如果浏览器无法显示图像，因为它是无效的或不支持的类型。
    在这些情况下，浏览器会用该元素的 **`alt`** 属性定义的文本来替换图像。

!!! warn "注意事项"
    省略 **`alt`** 属性表明该图像是内容的关键部分，但没有等效的文本可用。把这个属性设置为空字符串 (`alt=""`)，表明该图像不是内容的关键部分，非可视化浏览器在渲染的时候可能会忽略它。

```html
<!-- 全局链接地址 -->
<img src="https://dookbook.info/static/img/logo-tail.svg" alt="Dookbook logo">

<!-- 本地绝对路径 -->
<img src="/static/img/logo-tail.svg" alt="Dookbook logo">

<!-- 本地相对路径 -->
<img src="static/img/logo-tail.svg" alt="Dookbook logo">
```

## 支持的图像格式

HTML 标准并没有给出必须支持的图像格式的列表，因此每个用户代理支持一组不同的格式。

| 浏览器 | 支持的图像格式 |
| :-- | :-- |
| [Chrome](/zh-hans/glossary/Google_Chrome) | [[PNG]], [[JPEG]], [[GIF]] (包括动态的GIF), BMP, ICO, [[WebP]], [[SVG]], APNG |
| [Safari](/zh-hans/glossary/Apple_Safari) | [[PNG]], [[JPEG]], [[GIF]] (包括动态的GIF), BMP, ICO, ~~WebP~~, [[SVG]], APNG |
| Firefox | [[PNG]], [[JPEG]], [[GIF]] (包括动态的GIF), BMP, ICO, [[WebP]], [[SVG]], APNG |

## 图像加载错误

如果在尝试加载或渲染图像时发生错误，并且已配置`onerror`事件处理程序来处理该`error`事件，则将调用该事件处理程序。这可能在许多情况下发生，包括：

- 该`src`属性为空或为 [[`null`]]。
- 指定的`src` URL与用户当前所在页面的URL相同。
- 指定的图像以某种方式被破坏，导致无法加载。
- 指定图像的元数据已损坏，无法检索其尺寸，并且在`<img>`元素的属性中未指定尺寸。
- 指定的图像采用用户代理不支持的格式。

## 图像链接

本示例说明如何将图像转换为链接。

```html
<a href="https://dookbook.info">
  <img src="https://dookbook.info/static/img/logo-tail.svg" alt="Visit the Dookbook site">
</a>
```

## 指定高度和宽度的图像

使用 **`height`** 和 **`width`** 属性来指定图像高度和宽度。

```html
<img src="https://dookbook.info/static/img/logo-tail.svg" alt="Dookbook Logo" height="128" width="256">
```

## 使用 `srcset` 属性

**`srcset`**属性值是以*逗号分隔*的字符串来指定**用户代理（即浏览器）可能使用的图像备选项**。每一个字符串由以下组成：

1. 一个图像的URL。
2. 可选的，空格后跟以下的其一：
    - 一个**宽度描述符**，这是一个正整数，后面紧跟 **`w`** 符号。该整数宽度除以 *`sizes`* 属性给出的资源大小来计算得到有效的像素密度，即换算成和*`x`*描述符等价的值。
    - 一个**像素密度描述符**，这是一个正浮点数，后面紧跟 **`x`** 符号。
    - 如果没有指定源描述符，那它会被指定为默认的 **`1x`**。

在相同的 `srcset` 属性中混合使用宽度描述符和像素密度描述符时，会导致该值无效。重复的描述符（比如，两个源在相同的`srcset`两个源都是 `2x`）也是无效的。

浏览器会选择在特定条件下(比如用户设置或当前带宽)显示大部分适配的图片。

```html
<img src="dookbook-logo-tail.svg" alt="Dookbook Logo" srcset="dookbook-logo-tail.svg 2x">
```

## 响应式图像提示（使用 `srcset` 和 `sizes` 属性）

**`srcset`**属性值以*逗号分隔*的字符串来表示**资源大小**。每一个资源大小包括：

1. 一个**媒体条件**。最后一项一定是被忽略的。
2. 一个**资源尺寸的值**。资源尺寸的值被用来指定图像的预期尺寸。当`srcset`使用 *`w`* 描述符
   时，用户代理即浏览器使用当前图像大小来选择`srcset`中合适的图像URL。被选中的尺寸影响图像的显示大小（如果没有CSS样式被应用的话）。

在支持 `srcset` 的用户代理中，当使用 *`w`* 描述符时，`src` 属性会被忽略。当匹配了媒体条件 (`min-width: 600px`) 时，图像将宽 `200px`，否则宽 `50vw`（视图宽度的50%）。

```html
<img src="logo-200.png"
     alt="Logo"
     srcset="logo-200.png 200w,logo-400.png 400w"
     sizes="(min-width: 600px) 200px, 50vw">
```

可参考[`<picture>`](/zh-hans/webfrontend/<picture>)元素。

## 无障碍建议

### 有意义的替代说明 (`title`属性)

**`alt`**属性的值应清楚简洁地描述图像的内容。它不应描述图像本身的存在或图像的文件名。如果由于图像没有文本等价而故意关闭了`alt`属性，请考虑使用其他方法来呈现图像试图传达的内容。

不要这样：

```html
<img alt="一张图片" src="logo.jpg">
```

要这样：

```html
<img alt="Logo" src="logo.jpg">
```

当图像上没有`alt`属性时，某些屏幕阅读器可能会声明图像的*文件名*。如果文件名不代表图像内容，这可能会造成混乱。

### `title`属性

**[`title`](/zh-hans/webfrontend/title_attribute)** 属性不能替代 *`alt`*属性。另外，避免在同一张图片上声明的`title`属性中复制`alt`属性的值。
这样做可能会使某些屏幕阅读器两次宣布该描述，从而造成混乱的体验。

`title`属性也不应用作图像的`alt`描述的辅助字幕信息。如果图像需要字幕，请结合使用 *[`<figure>`](/zh-hans/webfrontend/<figure>)* 和
*[`<figcaption>`](/zh-hans/webfrontend/<figcaption>)* 元素。

### `alt` 与 `title`属性区别

图片中的 **`alt`属性**是在图片不能正常显示时出现的文本提示。

图片中的 **[`title`](/zh-hans/webfrontend/title_attribute)属性**是在鼠标在移动到元素上的文本提示。

## 与 CSS 的交互

关于 CSS，`<img>` 是一个替换元素。它没有基线，这意味着当在一个行内格式的上下文中使用 `vertical-align: baseline` 时，图像的底部将会与容器的基线对齐。

根据它的类型，图像可能会有一个本征维数（intrinsic dimension），但这不是一个必要条件：SVG图像就没有，而光栅图像有。

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<img>` | 支持 | 支持 | 支持 |
