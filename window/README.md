# NaN - Not a Number

This is property of global `window` object. there is one method also related to this property `isNaN()` which tells whether a given value is number of not. For more details visit [MDN Website](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN).

### Demonstration

```
console.log(isNaN(5))                   // Output: false
console.log(isNaN('5'))                 // Output: false
console.log(isNaN('a'))                 // Output: true
```

_Note: In second statement we had string but it does not care. It's motive is whether given value is valid number or not._

