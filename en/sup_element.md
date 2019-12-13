TOPICS: <sup>
AUTHORS: Masahiro Fujimoto; mfujimot@gmail.com; github:mfuji09
         Sphinx; SphinxKnight@github.com; github:SphinxKnight
         Bryan Lloyd; b-lloyd@github.com; github:b-lloyd
         Yuhei Yasuda; yuhei.yasuda1003@gmail.com; github:yuheiy
         Eric Shepherd; eshepherd@mozilla.com; github:a2sheppy
         Teoli; teoli@mozilla.net; mdn:teoli
         Michael[tm] Smith; mike@w3.org; github:sideshowbarker
         Karen Scarfone; kscarfone@mozilla.net; mdn:kscarfone
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Jonathan Wilsson; jwilsson@github.com; github:jwilsson

# `<sup>`

The **HTML Superscript element (`<sup>`)** specifies inline text which is to be displayed as superscript
for solely typographical reasons. Superscripts are usually rendered with
a raised baseline using smaller text.

|  |  |
| :-- | :-- |
| **Content categories** | Flow content, phrasing content, palpable content.|
| **Permitted content** Phrasing content.|
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts phrasing content.|
| **Permitted ARIA roles** | Any |
| **DOM interface** | `HTMLElement` |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

The `<sup>` element should only be used for typographical reasons—that is, to change the position of
the text to comply with typographical conventions or standards, rather than
solely for presentation or appearance purposes.

For example, to style the wordmark] of a business or product which uses a raised baseline should
be done using CSS (most likely `vertical-align`) rather than `<sup>`. This would be done using,
for example, `vertical-align: super` or, to shift the baseline up 50%, `vertical-align: 50%`.

Appropriate use cases for `<sup>` include (but aren't necessarily limited to):

- Displaying exponents, such as "x^3^." It may be worth considering the use of MathML] for
these, especially in more complex cases. See Exponents] under Examples] below.
- Displaying superior lettering], which is used in some languages when rendering certain abbreviations.
For example, in French, the word "mademoiselle" can be abbreviated "M^lle^"); this is an
acceptable use case. See Superior lettering] for examples.
- Representing ordinal numbers, such as "4^th^"
instead of "fourth." See Ordinal numbers] for examples.

## Examples

### Exponents

Exponents, or powers of a number, are among the most common uses of superscripted text. For example:

```html
<p>One of the most common equations in all of physics is
<var>E</var>=<var>m</var><var>c</var><sup>2</sup>.<p>
```

### Superior Lettering

Superior lettering is not technically the same thing as superscript. However, it is common to use
`<sup>` to present superior lettering in HTML. Among the most common uses of superior lettering is
the presentation of certain abbreviations in French:

```html
<p>Robert a présenté son rapport à M<sup>lle</sup> Bernard.</p>
```

### Ordinal Numbers

Ordinal numbers, such as "fourth" in English or "quinto" in Spanish may be abbreviated using numerals
and language-specific text rendered in superscript:

```html
<p>The ordinal number "fifth" can be abbreviated in various
languages as follows:</p>
<ul>
  <li>English: 5<sup>th</sup></li>
  <li>French: 5<sup>ème</sup></li>
</ul>
```
