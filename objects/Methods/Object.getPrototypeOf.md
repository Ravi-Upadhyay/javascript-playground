# Object.getPrototypeOf Method:

- This method is to see prototype of any object. 
- Every object has `\_\_proto\_\_` property which refers to the prototype of that object. 
- But, recommended way to do so is using `getPrototypeOf()` method.

### Syntax:

```javascript

Object.getPrototypeOf(__object-name-space__);
```

### Example:

```javascript
/*EXAMPLE-1 Using __proto__ and getPrototypeOf()*/
var Person = new Object({                   // { name    : "Ravi" }
  name    : "Ravi"                          
});                                         


var Person1 = Object.create(Person);        // {}
Person1.name;                               // "Ravi"
Person1.__proto__;                          // { name  : "Ravi" }
Object.getPrototypeOf(Person1);             // { name  : "Ravi" }, recommended way
```