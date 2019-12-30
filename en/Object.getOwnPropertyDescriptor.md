TOPICS: Object.getOwnPropertyDescriptor
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Object.getOwnPropertyDescriptor()`

The **`Object.getOwnPropertyDescriptor()`** method returns a property descriptor for an own property
(that is, one directly present on an object and not in the object's prototype chain) of a given object.

## Syntax

```javascript
Object.getOwnPropertyDescriptor(obj, prop)
```

| parameter | Description |
| :-- | :-- |
| `obj` | The object in which to look for the property. |
| `prop` | The name or `Symbol` of the property whose description is to be retrieved. |

**Return value**: A property descriptor of the given property if it exists on the object,
`undefined` otherwise.

## Description

This method permits examination of the precise description of a property. A property in JavaScript
consists of either a string-valued name or a `Symbol` and a property descriptor. Further
information about property descriptor types and their attributes can be found in [`Object.defineProperty()`](/en/webfrontend/Object.defineProperty).

A property descriptor is a record with some of the following attributes:

| Attributes | Description |
| :-- | :-- |
| **`value`** | The value associated with the property (data descriptors only).
| **`writable`** | `true` if and only if the value associated with the property may be changed (data descriptors only).
| **`get`** | A function which serves as a getter for the property, or `undefined` if there is no getter (accessor descriptors only).
| **`set`** | A function which serves as a setter for the property, or `undefined` if there is no setter (accessor descriptors only).
| **`configurable`** | `true` if and only if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.
| **`enumerable`** | `true` if and only if this property shows up during enumeration of the properties on the corresponding object.

## Examples

```javascript
var o, d;

o = { get foo() { return 17; } };
d = Object.getOwnPropertyDescriptor(o, 'foo');
// d is {
//   configurable: true,
//   enumerable: true,
//   get: /*the getter function*/,
//   set: undefined
// }

o = { bar: 42 };
d = Object.getOwnPropertyDescriptor(o, 'bar');
// d is {
//   configurable: true,
//   enumerable: true,
//   value: 42,
//   writable: true
// }

o = { [Symbol.for('baz')]: 73 }
d = Object.getOwnPropertyDescriptor(o, Symbol.for('baz'));
// d is {
//   configurable: true,
//   enumerable: true,
//   value: 73,
//   writable: true
// }

o = {};
Object.defineProperty(o, 'qux', {
  value: 8675309,
  writable: false,
  enumerable: false
});
d = Object.getOwnPropertyDescriptor(o, 'qux');
// d is {
//   value: 8675309,
//   writable: false,
//   enumerable: false,
//   configurable: false
// }
```

## NotesSection

In ES5, if the first argument to this method is not an object (a primitive), then it will cause
a `TypeError`. In ES2015, a non-object first argument will be coerced to an object at first.

```javascript
Object.getOwnPropertyDescriptor('foo', 0);
// TypeError: "foo" is not an object  // ES5 code

Object.getOwnPropertyDescriptor('foo', 0);
// Object returned by ES2015 code: {
//   configurable: false,
//   enumerable: true,
//   value: "f",
//   writable: false
// }
```
