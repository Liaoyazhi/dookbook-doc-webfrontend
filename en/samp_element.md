TOPICS: <samp>

# `<samp>`

The **HTML Sample Element (`<samp>`)** is used to enclose inline text which represents sample
(or quoted) output from a computer program. Its contents are typically rendered using the browser's
default monospaced font (such as Courier] or Lucida Console).

|  |  |
| :-- | :-- |
| **Content categories** | Flow content, phrasing content, palpable content. |
| **Permitted content** | Phrasing content.|
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts phrasing content. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | `HTMLElement` |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

You can use a CSS rule to override the browser's default font face for the `<samp>` element; however,
it's possible that the browser's preferences may take precedence over any CSS you specify.

The CSS to override the default font face would look like this:

```css
samp {
  font-family: "Courier";
}
```

!!! warn "Don't try this at home"
    If you need an element which will serve as a container for output generated by your website or
    app's JavaScript code, you should instead use the [`<output>`](/en/webfrontend/<output>) element.

## Examples

### Basic example

In this simple example, a paragraph includes an example of the output of a program.

```html
<p>When the process is complete, the utility will output the text
<samp>Scan complete. Found <em>N</em> results.</samp> You can then
proceed to the next step.</p>
```

### Sample output including user input

You can nest the [`<kbd>`](/en/webfrontend/<kbd>) element within a `<samp>` block to present
an example that includes text entered by the user. For example, consider this text presenting
a transcript of a Linux (or macOS) console session:

```html
<pre>
<samp><span class="prompt">mike@interwebz:~$</span><kbd>md5 -s "Hello world"</kbd>
MD5 ("Hello world") = 3e25960a79dbc69b674cd4ec67a72c62

<span class="prompt">mike@interwebz:~$</span> <span class="cursor">█</span></samp></pre>
```

Note the use of [`<span>`](/en/webfrontend/<span>) to allow customization of the appearance of
specific portions of the sample text such as the shell prompts and the cursor. Note also the use of
[`<kbd>`](/en/webfrontend/<kbd>) to represent the command the user entered at the prompt
in the sample text.

The CSS that achieves the appearance we want is:

```css
.prompt {
  color: #b00;
}

samp > kbd {
  font-weight: bold;
}

.cursor {
  color: #00b;
}
```

This simply gives the prompt and cursor fairly subtle colorization and emboldens the
keyboard input within the sample text.