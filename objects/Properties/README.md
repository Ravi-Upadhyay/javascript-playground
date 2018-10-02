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
- `Object.defineProperty()` method can be used to define properties precisely with some more options. See [Object.defineProperty()](./Methods/Object.defineProperty.md).


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

## Properties:

- [Check for properties](CheckForProperties.md)
