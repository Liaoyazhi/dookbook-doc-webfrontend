TOPICS: String.concat
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.concat()`

The **`concat()`** method concatenates the string arguments to the calling string and returns a new string.

## Syntax

```javascript
str.concat(str2 [, ...strN])
```

| parameter | Description |
| :-- | :-- |
| `str2 [, ...strN]` | Strings to concatenate to `str`. |

**Return value**: A new string containing the combined text of the strings provided.

## Description

The `concat()` function concatenates the string arguments to the calling string and returns a new
string. Changes to the original string or the returned string don't affect the other.

If the arguments are not of the type string, they are converted to string values before concatenating.

## Examples

### Using `concat()`

The following example combines strings into a new string.

```javascript
let hello = 'Hello, '
console.log(hello.concat('Kevin', '. Have a nice day.'))
// Hello, Kevin. Have a nice day.

let greetList = ['Hello', ' ', 'Venkat', '!']
"".concat(...greetList)  // "Hello Venkat!"

"".concat({})    // [object Object]
"".concat([])    // ""
"".concat(null)  // "null"
"".concat(true)  // "true"
"".concat(4, 5)  // "45"
```

## Performance

It is strongly recommended that the assignment operators (`+`, `+=`) are used instead of the
`concat()` method.

According to this performance test, the assignment operators are several times faster.
