TOPICS: <style>
AUTHORS: Alfred Myers; alfredmyers@github.com; github:alfredmyers
         ExE Boss; ExE-Boss@github.com; github:ExE-Boss
         Chris Mills; chrisdavidmills@mozilla.net; mdn:chrisdavidmills
         Tang Yun; ntutangyun@gmail.com; github:ntutangyun
         Sphinx; SphinxKnight@github.com; github:SphinxKnight
         Eric Shepherd; eshepherd@mozilla.com; github:a2sheppy
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Michael[tm] Smith; mike@w3.org; github:sideshowbarker
         PhistucK; phistuck@mozilla.net; mdn:phistuck
         Teoli; teoli@mozilla.net; mdn:teoli
         Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Jérémie Patonnier; Jeremie@mozilla.net; mdn:Jeremie
         一丝; yisibl@mozilla.net; mdn:yisibl
         Karen Scarfone; kscarfone@mozilla.net; mdn:kscarfone
         Keiichi; ethertank@mozilla.net; mdn:ethertank
         Trevor Hobson; trevorhobson@github.com; github:trevorhobson
         Masahiko Imanaka; marsf@github.com; github:marsf
         Jonathan Wilsson; jwilsson@github.com; github:jwilsson

# `<style>`

The **HTML `<style>` element** contains style information for a document, or part of a document.
It contains CSS, which is applied to the contents of the document containing the `<style>` element.

The `<style>` element can be included inside the [`<head>`](/en/webfrontend/<head>) or [`<body>`](/en/webfrontend/<body>)
of the document, and the styles will still be applied, however it is recommended that you include your
styles in the [`<head>`](/en/webfrontend/<head>) for organizational purposes — it is a lot better to
separate your content from your presentation as much as possible. Even better, put your styles in
external stylesheets and apply them using [`<link>`](/en/webfrontend/<link>) elements.

If you include multiple `<style>` and [`<link>`](/en/webfrontend/<link>) elements in your document,
they will be applied to the DOM in the order they are included in the document — make sure you
include them in the correct order, to avoid unexpected cascade issues.

In the same manner as [`<link>`](/en/webfrontend/<link>) elements, `<style>` elements can include
media attributes that contain media queries, allowing you to selectively apply internal stylesheets
to your document depending on media features such as viewport width.

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `type` | This attribute defines the styling language as a MIME type (charset should not be specified). This attribute is optional and defaults to `text/css` if it is not specified — there is very little reason to include this in modern web documents.
| `media` | This attribute defines which media the style should be applied to. Its value is a media query, which defaults to `all` if the attribute is missing.
| `nonce` | A cryptographic nonce (number used once) used to whitelist inline styles in a style-src Content-Security-Policy. The server must generate a unique nonce value each time it transmits a policy. It is critical to provide a nonce that cannot be guessed as bypassing a resource’s policy is otherwise trivial.
| `title` | This attribute specifies alternative style sheet sets.

## Styling with CSS

The `<style>` element itself has no visual representation, therefore it has no styling considerations.

## Examples

### A simple stylesheet

In the following example, we apply a very simple stylesheet to a document:

```html
<!doctype html>
<html>
<head>
<style>
p {
  color: red;
}
</style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

### Multiple style elements

In this example we've included two `<style>` elements — notice how the conflicting declarations
in the later `<style>` element override those in the earlier one, if they have equal specificity.

```html
<!doctype html>
<html>
<head>
  <style>
  p {
    color: white;
    background-color: blue;
    padding: 5px;
    border: 1px solid black;
  }
  </style>
  <style>
  p {
    color: blue;
    background-color: yellow;
  }
  </style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

### Including a media query

In this example we build on the previous one, including a media attribute on the second `<style>`
element so it is only applied when the viewport is less than 500px in width.

```html
<!doctype html>
<html>
<head>
  <style>
    p {
      color: white;
      background-color: blue;
      padding: 5px;
      border: 1px solid black;
    }
  </style>
  <style media="all and (max-width: 500px)">
    p {
      color: blue;
      background-color: yellow;
    }
  </style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | Metadata content, and if the `scoped` attribute is present: flow content. |
| **Permitted content** | Text content matching the `type` attribute, that is `text/css`. |
| **Tag omission** | Neither tag is omissible. |
| **Permitted parents** | Any element that accepts metadata content. |
| **Permitted ARIA roles** | None |
| **DOM interface** | `HTMLStyleElement` |
