TOPICS: Element.matches
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.matches()`

The **`matches()`** method checks to see if the `Element` would be selected by the provided
`selectorString` -- in other words -- checks if the element "is" the selector.

## Syntax

```javascript
var result = element.matches(selectorString);
```

| parameter | Description |
| :-- | :-- |
| `selectorString` | is a string representing the selector to test.

**Return value**: result is a `Boolean`.

## Exceptions

|  |  |
| :-- | :-- |
| `SYNTAX_ERR` | The specified selector string is invalid.

## Examples

```html
<ul id="birds">
  <li>Orange-winged parrot</li>
  <li class="endangered">Philippine eagle</li>
  <li>Great white pelican</li>
</ul>

<script type="text/javascript">
  var birds = document.getElementsByTagName('li');

  for (var i = 0; i < birds.length; i++) {
    if (birds[i].matches('.endangered')) {
      console.log('The ' + birds[i].textContent + ' is endangered!');
    }
  }
</script>
```

This will log "The Philippine eagle is endangered!" to the console, since the element has indeed a
`class` attribute with value `endangered`.

## Polyfill

For browsers that do not support `Element.matches()` or `Element.matchesSelector(`), but include
support for `document.querySelectorAll()`, a polyfill exists:

```javascript
if (!Element.prototype.matches) {
  Element.prototype.matches =
      Element.prototype.matchesSelector ||
      Element.prototype.mozMatchesSelector ||
      Element.prototype.msMatchesSelector ||
      Element.prototype.oMatchesSelector ||
      Element.prototype.webkitMatchesSelector ||
      function(s) {
        var matches = (this.document || this.ownerDocument).querySelectorAll(s),
            i = matches.length;
        while (--i >= 0 && matches.item(i) !== this) {}
        return i > -1;
      };
}
```

However, given the practicality of supporting older browsers, the following should suffice for
most (if not all) practical cases (i.e. IE9+ support).

```javascript
if (!Element.prototype.matches) {
  Element.prototype.matches = Element.prototype.msMatchesSelector ||
                              Element.prototype.webkitMatchesSelector;
}
```
