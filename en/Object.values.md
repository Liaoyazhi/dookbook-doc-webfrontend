TOPICS: Object.values
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Object.values()`

The **`Object.values()`** method returns an array of a given object's own enumerable property
values, in the same order as that provided by a `for...in` loop (the difference being that a
for-in loop enumerates properties in the prototype chain as well).

## Syntax

```javascript
Object.values(obj)
```

| parameter | Description |
| :-- | :-- |
| `obj` | The object whose enumerable own property values are to be returned. |

**Return value**: An array containing the given object's own enumerable property values.

## Description

`Object.values()` returns an array whose elements are the enumerable property values found on the
object. The ordering of the properties is the same as that given by looping over the property values
of the object manually.

## Examples

```javascript
var obj = { foo: 'bar', baz: 42 };
console.log(Object.values(obj)); // ['bar', 42]

// array like object
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.values(obj)); // ['a', 'b', 'c']

// array like object with random key ordering
// when we use numeric keys, the value returned in a numerical order according to the keys
var an_obj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.values(an_obj)); // ['b', 'c', 'a']

// getFoo is property which isn't enumerable
var my_obj = Object.create({}, { getFoo: { value: function() { return this.foo; } } });
my_obj.foo = 'bar';
console.log(Object.values(my_obj)); // ['bar']

// non-object argument will be coerced to an object
console.log(Object.values('foo')); // ['f', 'o', 'o']
```

## Polyfill

To add compatible `Object.values` support in older environments that do not natively support it,
you can find a Polyfill in the [tc39/proposal-object-values-entries](https://github.com/tc39/proposal-object-values-entries)
or in the [es-shims/Object.values](https://github.com/es-shims/Object.values) repositories.
