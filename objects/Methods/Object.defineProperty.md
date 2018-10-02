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
- 

### Syntax:

```javascript

Object.defineProperty(obj, prop, descriptor);

```

### Example: