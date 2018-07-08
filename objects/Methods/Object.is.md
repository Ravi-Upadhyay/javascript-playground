# Object.is() Method:

It tells whether two values are the same value. is a new utility for checking strict equality of two values
but without the nuanced exceptions that `===` has for `NaN` and `-0` values. Goto [MDN Website](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is) for more details

### Description 

Two values are the same if one of the following holds:

* both undefined
* both null
* both true or both false
* both strings of the same length with the same characters in the same order
* both the same object
* both numbers and
    * both +0
    * both -0
    * both NaN
    * or both non-zero and both not NaN and both have the same value

### Syntax

```
Object.is(value1, value2)
```

### Polyfill for Object.is()
```
if (!Object.is) {
    Object.is = function(v1, v2) {
        
        // test for `-0`
        if (v1 === 0 && v2 === 0) {
            return 1 / v1 === 1 / v2;
        }

        // test for `NaN`
        if (v1 !== v1) {
            return v2 !== v2;
        }

        // everything else
        return v1 === v2;
    };
}
```