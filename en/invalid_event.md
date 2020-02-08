TOPICS: oninvalid
        invalid
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `invalid` Event

The **`oninvalid`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`invalid` events.

The `invalid` event fires when a submittable element has been checked and doesn't satisfy its
constraints. The validity of submittable elements is checked before submitting their owner form, or
after the `checkValidity()` method of the element or its owner form is called.

## Syntax

```javascript
target.oninvalid = functionRef;
var functionRef = target.oninvalid;
```

`functionRef` is a function name or a function expression. The function receives a `Event`
object as its sole argument.

## Example

This example demonstrates `oninvalid` and `onsubmit` event handlers on a form.

```html
<form id="form">
  <p id="error" hidden>Please fill out all fields.</p>

  <label for="city">City</label>
  <input type="text" id="city" required>

  <button type="submit">Submit</button>
</form>
<p id="thanks" hidden>Your data has been received. Thanks!</p>
```

```javascript
const form = document.getElementById('form');
const error = document.getElementById('error');
const city = document.getElementById('city');
const thanks = document.getElementById('thanks');

city.oninvalid = invalid;
form.onsubmit = submit;

function invalid(event) {
  error.removeAttribute('hidden');
}

function submit(event) {
  form.setAttribute('hidden', '');
  thanks.removeAttribute('hidden');

  // For this example, don't actually submit the form
  event.preventDefault();
}
```
