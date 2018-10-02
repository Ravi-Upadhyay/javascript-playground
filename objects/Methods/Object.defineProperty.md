# defineProperty Method:

- Precisely defines new property directly onto object or modifies existing property.
- Call this method on `Object constructor` rather than on `instance` of Object.
- It returns the object.

### Description:
- Normal property addition through assignment creates properties which (1) show up during property enumeration (for...in loop or Object.keys method), (2) whose values may be changed, and (3) which may be deleted. 
- This method allows these extra details to be changed from default.
- Property descriptors have two flavours
    - **Data descriptors:**  Is a property that has a value, which may or may not be writable.
    - **Accessor descriptors:** Is a property described by getter-setter pair  of functions.
- Please visit [property](../properties) for more details about this.
- `Object.freeze()` can be used to freeze objects as writable will not affect objects.[freeze()](Object.freeze.md)

### Syntax:

```javascript

Object.defineProperty(obj, prop, descriptor);

```

### Example:

```javascript

/* EXAMPLE-DP-1 Make property of object not writable */

var obj = {
    prop    : 'someValue'
};

Object.defineProperty(obj, prop, {
    writable    : false
});

obj.prop = 'anotherValue';                          // 'someValue', it will not changed. If in strict mode it 
                                                    // will through error.

// If property is pointing to another object.

var obj = {
    prop    : {
        nProp   : 'someValue'
    }
};

Object.defineProperty(obj, 'prop', {
    writable    : false
});

obj.prop.nProp = 'anotherValue';                    // 'anotherValue', because here prop is nothing but pointer.

// However, we can do this by
Object.freeze(obj.prop);






```