TOPICS: <var>

# `<var>`

The **HTML Variable element (`<var>`)** represents the name of a variable in a mathematical
expression or a programming context. It's typically presented using an italicized version of the
current typeface, although that behavior is browser-dependent.

|  |  |
| :-- | :-- |
| **Content categories** | Flow content, phrasing content, palpable content.|
| **Permitted content** | Phrasing content.|
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts phrasing content.|
| **Permitted ARIA roles** | Any |
| **DOM interface** | `HTMLElement` |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

### Related elements

Other elements that are used in contexts in which `<var>` is commonly used include:

- [`<code>`](/en/webfrontend/<code>): The HTML Code element
- [`<kbd>`](/en/webfrontend/<kbd>): The HTML Keyboard input element
- [`<samp>`](/en/webfrontend/<samp>): The HTML Sample Output element

If you encounter code that is mistakenly using `<var>` for style purposes rather than semantic
purposes, you should either use a [`<span>`](/en/webfrontend/<span>) with appropriate CSS or,
an appropriate semantic element among the following:

- [`<em>`](/en/webfrontend/<em>)
- [`<i>`](/en/webfrontend/<i>)
- [`<q>`](/en/webfrontend/<q>)

### Default style

Most browsers apply font-style to "italic" when rendering `<var>`.
This can be overridden in CSS, like this:

```css
var {
  font: bold 15px "Courier", "Courier New", monospace;
}
```

## Examples

### Basic example

Here's a simple example, using `<var>` to denote variable names in a mathematical equation.

```html
<p>A simple equation:
  <var>x</var> = <var>y</var> + 2 </p>
```

### Overriding the default style

Using CSS, you can override the default style for the `<var>` element. In this example, variable
names are rendered using bold Courier if it's available, otherwise it
falls back to the default monospace font.

```css
var {
  font: bold 15px "Courier", "Courier New", monospace;
}
```

```html
<p>The variables <var>minSpeed</var> and <var>maxSpeed</var> control
   the minimum and maximum speed of the apparatus in revolutions
   per minute (RPM).</p>
```

This HTML uses `<var>` to enclose the names of two variables.
