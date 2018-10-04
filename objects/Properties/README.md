# Properties:

//TODO: Proper description of properties

## Index:

- Description
- Properties
- Properties of Object

## Description:

- Here we will discuss about properties in general.
- Properties are key value pair on object-name-space.
- See the diagram below to know about how to create or access properties.
- `Object.defineProperty()` method can be used to define properties precisely with some more options. See [Object.defineProperty()](../Methods/Object.defineProperty.md).


![Properties in JS](https://github.com/Ravi-Upadhyay/javascript-playground/blob/master/objects/Properties/Resources/Properties-in-JS.jpg)  

```javascript

var obj = {};

/* EXAMPLE-1: create property by Dot (.) Notation */

obj.byDotAcc = 1;

/* EXAMPLE-2: create property by Bracket ([]) Notation */

//simple way
obj['byBrkAcc'] = 2;

//or, dynamic
var key = 'byBrkAcc';
obj[key] = 2;

/* EXAMPLE-3: create using Object.defineProperty() Method */

Object.defineProperty(obj,'byDefProp',{
    value   : 3,
    enumerable  : false,
    writable    : true,
    configurable: false,
});

obj;                                                            // {
                                                                //      byDotAcc    : 1,
                                                                //      byBrkAcc    : 2,
                                                                //      byDefProp   : 3
                                                                // }

```

### Getter: 

- Sometimes it is desirable to allow access to a property that returns a dynamically computed value, or you may want to reflect the status of an internal variable without requiring the use of explicit method calls.
- It is not possible to simultaneously have a `getter` bound to a property and have that property actually hold a `value`, although it is possible to use a getter and a setter in conjunction to create a type of `pseudo-property`.
- A getter can be removed using the `delete` operator.

```javascript

/* EXAMPLE-GTR-1 Simple way to define getter property */

var obj = {
  log: ['example','test'],
  get latest() {
    if (this.log.length == 0) return undefined;
    return this.log[this.log.length - 1];
  }
}
console.log(obj.latest);                                    // "test".

/* EXAMPLE-GTR-2 Define getter property using defineProperty() */

obj.defineProperty(obj, 'latest',{
    get : function(){
        if (this.log.length == 0) return undefined;
        return this.log[this.log.length - 1];
    }
});

```

### Setter:

- In JavaScript, a setter can be used to execute a function whenever a specified property is attempted to be changed.
- Setters are most often used in conjunction with getters to create a type of `pseudo-property`.
- It is not possible to simultaneously have a setter on a property that holds an actual value.

```javascript



```

## Properties of global Object:

- [Check for properties](CheckForProperties.md)
