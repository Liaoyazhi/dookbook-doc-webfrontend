TOPICS: <a>

# HTML Anchor Element: `<a>`

The **HTML `<a>` element** (or **anchor element**), along with it's `href` attribute, creates a
hyperlink to other web pages, files, locations within the same page, email addresses, or any other URL.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | Flow content, phrasing content, interactive content, palpable content. |
| **Permitted content** | Transparent, containing either flow content (excluding interactive content) or phrasing content.
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts phrasing content, or any element that accepts flow content, but always excluding `<a>` elements (according to the logical principle of symmetry, if `<a>` tag, as a parent, can not have interactive content, then the same `<a>` content can not have `<a>` tag as its parent).|
| **Permitted ARIA roles** | [`button`](https://w3c.github.io/aria/#button), [`checkbox`](https://w3c.github.io/aria/#checkbox), [`menuitem`](https://w3c.github.io/aria/#menuitem), [`menuitemcheckbox`](https://w3c.github.io/aria/#menuitemcheckbox), [`menuitemradio`](https://w3c.github.io/aria/#menuitemradio), [`option`](https://w3c.github.io/aria/#option), [`radio`](https://w3c.github.io/aria/#radio), [`switch`](https://w3c.github.io/aria/#switch), [`tab`](https://w3c.github.io/aria/#tab), [`treeitem`](https://w3c.github.io/aria/#treeitem) |
| **DOM interface** | `HTMLAnchorElement` |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_attributes).

| Attribute | Description |
| :-- | :-- |
| `download` | This attribute instructs browsers to download a URL instead of navigating to it, so the user will be prompted to save it as a local file. If the attribute has a value, it is used as the pre-filled file name in the Save prompt (the user can still change the file name if they want). There are no restrictions on allowed values, though / and \ are converted to underscores. Most file systems limit some punctuation in file names, and browsers will adjust the suggested name accordingly.<br>**Note**:<br>This attribute only works for same-origin URLs, but never for [`file:`](https://en.wikipedia.org/wiki/File_URI_scheme) URIs.<br>Although HTTP(s) URLs need to be in the same-origin, `blob:` URLs and `data:` URLs are allowed so that content generated by JavaScript, such as pictures created in an image-editor Web app, can be downloaded.<br>If the HTTP header `Content-Disposition:` gives a different filename than this attribute, the HTTP header takes priority over this attribute.<br>If `Content-Disposition:` is set to `inline`, Firefox prioritizes `Content-Disposition`,like the filename case, while Chrome prioritizes the `download` attribute. |
| `href` | Contains a URL or a URL fragment that the hyperlink points to. URLs are not restricted to Web (HTTP)-based documents, but can use any protocol supported by the browser. For example, [`file:`](https://en.wikipedia.org/wiki/File_URI_scheme), `ftp:`, and `mailto:` work in most browsers. A URL fragment is a name preceded by a hash mark (`#`), which specifies an internal target location (an `id` of an HTML element) within the current document. See the examples with URLs, URL fragments, and multiple protocols below.|
| `hreflang` | This attribute indicates the human language of the linked resource. It is purely advisory, with no built-in functionality. Allowed values are determined by [BCP47](https://www.ietf.org/rfc/bcp/bcp47.txt).
| `ping` | Contains a space-separated list of URLs to which, when the hyperlink is followed, `POST` requests with the body PING will be sent by the browser (in the background). Typically used for tracking.|
| `referrerpolicy` | Indicates which referrer to send when fetching the URL:<br>`"no-referrer"` means the `Referer:` header will not be sent.<br>`"no-referrer-when-downgrade"` means no `Referer:` header will be sent when navigating to an origin without HTTPS. This is the default behavior.<br>`"origin"` means the referrer will be the origin of the page, not including information after the domain.<br>`"origin-when-cross-origin"` meaning that navigations to other origins will be limited to the scheme, the host and the port, while navigations on the same origin will include the referrer's path.<br>`'strict-origin-when-cross-origin'`<br>`"unsafe-url"` means the referrer will include the origin and path, but not the fragment, password, or username. This is unsafe because it can leak data from secure URLs to insecure ones. |
| `rel` | Specifies the relationship of the target object to the link object. The value is a space-separated list of link types.
| `target` | Specifies where to display the linked URL. It is a name of, or keyword for, a browsing context: a tab, window, or [`<iframe>`](/en/webfrontend/<iframe>). The following keywords have special meanings:<br>`_self`: Load the URL into the same browsing context as the current one. This is the default behavior.<br>`_blank`:  Load the URL into a new browsing context. This is usually a tab, but users can configure browsers to use new windows instead.<br>`_parent`: Load the URL into the parent browsing context of the current one. If there is no parent, this behaves the same way as `_self`.<br>`_top`: Load the URL into the top-level browsing context (that is, the "highest" browsing context that is an ancestor of the current one, and has no parent). If there is no parent, this behaves the same way as `_self`.<br> **Note:**<br>When using `target`, consider adding `rel="noreferrer"` to avoid exploitation of the<br>window.opener API. See Security concerns section<br>**Note:**<br>Linking to another page using `target="_blank"` will run the new page on the same process as<br>your page. If the new page is executing expensive JS, your page's performance may suffer.To avoid this use `rel="noopener"`.
| `type` | Specifies the media type in the form of a MIME type for the linked URL. It is purely advisory, with no built-in functionality. |

## Examples

### Linking to an external location

```html
<!-- anchor linking to external file -->
<a href="https://dookbook.info/">External Link</a>
```

### Linking to another section on the same page

```html
<!-- links to element on this page with id="attr-href" -->
<a href="#attr-href">Description of Same-Page Links</a>
```

### Creating an image link

```html
<a href="https://dookbook.info">
  <img src="https://dookbook.info/static/img/logo-tail.svg" alt="Dookbook logo" />
</a>
```

### Creating an email link

It's common to create links that open in the user's email program to allow them to send a new message.
This is done with a `mailto:` link. Here's a simple example:

```html
<a href="mailto:dookbook@zhiliaokeji.com">Send email to Dookbook</a>
```

For additional details about the `mailto` URL scheme, such as including the subject, body,
or other predetermined content, see Email links or [RFC 6068](https://tools.ietf.org/html/rfc6068).

### Creating a phone link

Offering phone links is helpful for users viewing web documents and laptops connected to phones.

```html
<a href="tel:+491570156">+49 157 0156</a>
```

For additional details about the `tel` URL scheme, see [RFC 3966](https://tools.ietf.org/html/rfc3966).

### Download Link

```html
<a href="<download-url>" download="<default-filename>" title="Hints">Download Text</a>
```

### Using the `download` attribute to save a `<canvas>` as PNG

If you want to let users download an HTML [`<canvas>`](/en/webfrontend/<canvas>) element as an image,
you can create a link with a `download` attribute and the canvas data as a file URL:

```javascript
var link = document.createElement('a');
link.textContent = 'download image';

link.addEventListener('click', function(ev) {
    link.href = canvas.toDataURL();
    link.download = "my_painting.png";
}, false);

document.body.appendChild(link);
```

You can see this in action at [jsfiddle.net/codepo8/V6ufG/2/](https://jsfiddle.net/codepo8/V6ufG/2/).

## Security and privacy concerns

Although `<a>` elements have many innocent uses, they can have undesirable consequences for user
security and privacy. See Referer header: privacy and security concerns
for more information and mitigations.

Using `target="_blank"` without `rel="noreferrer"` and `rel="noopener"` makes the website
vulnerable to `window.opener` API exploitation attacks, see the links section for description.

## Accessibility Concerns

### onclick events

Anchor TOPICS are often abused with the onclick event to create pseudo-buttons by setting **href**
to `"#"` or `"javascript:void(0)"` to prevent the page from refreshing.

These values cause unexpected behavior when copying/dragging links, opening links in a new tab/window,
bookmarking, and when JavaScript is still downloading, errors out, or is disabled. This also conveys
incorrect semantics to assistive technologies (e.g., screen readers). In these cases, it is
recommended to use a [`<button>`](/en/webfrontend/<button>) instead. In general you should only use
an anchor for navigation using a proper URL.

### External links and linking to non-HTML resources

Both links that open in a new tab or window via the `target="_blank"` declaration and links to
whose `href` value points to a file resource should include an indicator about the behavior that
will occur when the link is activated.

People experiencing low vision conditions, who are navigating with the aid of screen reading
technology, or who have cognitive concerns may become confused when the new tab, window,
or application is opened unexpectedly. Older versions of screen reading software may
not even announce the behavior.

### Link that opens a new tab or window

```html
<a target="_blank" href="https://www.wikipedia.org/">Wikipedia (opens in a new window)</a>
```

### Link to a non-HTML resource

```html
<a target="_blank" href="2017-annual-report.ppt">2017 Annual Report (PowerPoint)</a>
```

If an icon is used in place of text to signify this kind of links behavior, make sure it includes
an alternate description].

- WebAIM: Links and Hypertext - Hypertext Links
- MDN Understanding WCAG, Guideline 3.2 explanations
- [G200: Opening new windows and tabs from a link only when necessary | W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/G200.html)
- [G201: Giving users advanced warning when opening a new window | W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/G201.html)

### Skip links

A skip link, also known as skipnav, is an a element placed as close as possible to the opening
[`<body>`](/en/webfrontend/<body>) element that links to the beginning of the page's main content.
This link allows people to bypass content repeated throughout multiple pages on a website,
such as a website's header and primary navigation.

Skip links are especially useful for people who navigate with the aid of assistive technology
such as switch control, voice command, or mouth sticks/head wands, where the act of moving
through repetitive links can be a laborious task.

- [WebAIM: "Skip Navigation" Links](https://webaim.org/techniques/skipnav/)
- [How–to: Use Skip Navigation links - The A11Y Project](https://a11yproject.com/posts/skip-nav-links/)
- MDN Understanding WCAG, Guideline 2.4 explanations
- [Understanding Success Criterion 2.4.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)

### Size

Interactive elements such as links should provide an area large enough that it is easy to activate
them. This helps a variety of people, including people with motor control issues and people using
non-precise forms of input such as a stylus or fingers. A minimum interactive
size of 44 by 44 [CSS pixels](https://www.w3.org/TR/WCAG21/#dfn-css-pixels) is recommended.

- [Understanding Success Criterion 2.5.5: Target Size | W3C Understanding WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)
- [Target Size and 2.5.5 | Adrian Roselli](http://adrianroselli.com/2019/06/target-size-and-2-5-5.html)
- [Quick test: Large touch targets - The A11Y Project](https://a11yproject.com/posts/large-touch-targets/)

### Proximity

Large amounts of interactive content—including anchors—placed in close visual proximity to each
other should have space inserted to separate them. This spacing is beneficial for people who are
experiencing motor control issues, who may accidentally activate the wrong interactive
content while navigating.

Spacing may be created using CSS properties such as `margin`.

- [`Hand tremors and the giant-button-problem - Axess Lab`](https://axesslab.com/hand-tremors/)