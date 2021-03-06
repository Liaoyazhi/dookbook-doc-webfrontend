TOPICS: Boolean

# JavaScript `Boolean` Object

The **`Boolean`** object is an object wrapper for a `boolean` value.

## Syntax

```javascript
new Boolean([value])
```

| parameter | Description |
| :-- | :-- |
| `value` | The initial value of the `Boolean` object. |

## Description

The value passed as the first parameter is converted to a `boolean` value, if necessary. If the value
is omitted or is `0`, `-0`, [`null`](/en/webfrontend/null), `false`, `NaN`, [`undefined`](/en/webfrontend/undefined),
or the empty string (`""`), the object has an initial value of `false`. All other values,
including any object, an empty array (`[]`), or the string "`false`", create an object with an
initial value of `true`.

Do not confuse the primitive `Boolean` values `true` and `false` with the `true` and `false` values
of the `Boolean` object.

Any object of which the value is not [`undefined`](/en/webfrontend/undefined) or
[`null`](/en/webfrontend/null), including a `Boolean` object whose
value is `false`, evaluates to `true` when passed to a conditional statement. For example,
the condition in the following `if` statement evaluates to `true`:

```javascript
var x = new Boolean(false);
if (x) {
  // this code is executed
}
```

This behavior does not apply to `Boolean` primitives. For example, the condition in the following
`if` statement evaluates to `false`:

```javascript
var x = false;
if (x) {
  // this code is not executed
}
```

Do not use a `Boolean` object to convert a non-boolean value to a `boolean` value. To perform this task,
instead, use `Boolean` as a function, or a double NOT operator:

```javascript
var x = Boolean(expression);     // use this...
var x = !!(expression);          // ...or this
var x = new Boolean(expression); // don't use this!
```

If you specify any object, including a `Boolean` object whose value is `false`, as the initial value
of a `Boolean` object, the new `Boolean` object has a value of `true`.

```javascript
var myFalse = new Boolean(false);   // initial value of false
var g = Boolean(myFalse);       // initial value of true
var myString = new String('Hello'); // string object
var s = Boolean(myString);      // initial value of true
```

Do not use a `Boolean` object in place of a `Boolean` primitive.

!!! warn "Note"
    When the non-standard property `document.all` is used as an argument for this constructor,
    the result is a `Boolean` object with the value `false`. This property is legacy and non-standard
    and should not be used.

## `Boolean.prototype`

The `Boolean.prototype` property represents the prototype for the `Boolean`
constructor.

Property attributes of **`Boolean.prototype`**

|  |  |
| :--- | :--- |
| `Writable` | `no` |
| `Enumerable` | `no` |
| `Configurable` | `no` |

### `Boolean.prototype` Syntax

```javascript
Boolean.prototype.name=value
```

### `Boolean.prototype` Description

`Boolean` instances inherit from `Boolean`. You can use
the constructor's prototype object to add properties or methods to all
`Boolean` instances.

## Examples

### Creating `Boolean` objects with an initial value of `false`

```javascript
var bNoParam = new Boolean();
var bZero = new Boolean(0);
var bNull = new Boolean(null);
var bEmptyString = new Boolean('');
var bFalse = new Boolean(false);
```

### Creating Boolean objects with an initial value of `true`

```javascript
var bTrue = new Boolean(true);
var bTrueString = new Boolean('true');
var bFalseString = new Boolean('false');
var bSuLin = new Boolean('Su Lin');
var bArrayProto = new Boolean([]);
var bObjProto = new Boolean({});
```

## Truthy Values

In JavaScript, a **truthy** value is a value that is considered `true` when encountered in a
Boolean context. All values are truthy unless they are defined as falsy (i.e., except for `false`,
`0`, `""`, `null`, `undefined`, and `NaN`).

JavaScript uses type coercion in Boolean contexts.

Examples of truthy values in JavaScript (which will be coerced to true in boolean contexts,
and thus execute the `if` block):

```javascript
if (true)
if ({})
if ([])
if (42)
if ("0")
if (new Date())
if (-42)
if (12n)
if (3.14)
if (-3.14)
if (Infinity)
if (-Infinity)
```
