TOPICS: <param>

# `<param>`

The **HTML `<param>` element** defines parameters for an [`<object>`](/en/webfrontend/<object>) element.

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | None, it is an empty element. |
| **Tag omission** | As it is a void element, the start tag must be present and the end tag must not be present.|
| **Permitted parents** | An [`<object>`](/en/webfrontend/<object>) before any flow content. |
| **Permitted ARIA roles** | None |
| **DOM interface** | `HTMLParamElement` |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `name` | Name of the parameter.
| `value` | Specifies the value of the parameter.

## Examples

```html
<!-- Embed a flash movie with parameters -->
<object data="move.swf" type="application/x-shockwave-flash">
  <param name="foo" value="bar">
</object>
```
