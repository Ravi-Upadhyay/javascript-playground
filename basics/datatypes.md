# Datatypes in Javascript:
Programming languages all have built-in data structures, but these often differ from one language to another. We will list the built-in data structures available in JavaScript and what properties they have; these can be used to build other data structures. Wherever possible, comparisons with other languages are drawn.

---

## Index:

- Datatypes classification
- Points to ponder

---

## Datatypes classification:

- _Dynamic typing_ or _Loosely typed_  Variables in JavaScript are not directly associated with any particular value type.
- Data types
    * _Primitive data types_: All types except objects define immutable values (values, which are incapable of being changed). We refer to values of these types as "primitive values".

        1. `Boolean`
        2. `Null`
        3. `Undefined`
        4. `Number`
        5. `String`
        6. `Symbol` (New in ES6) ==TODO: Look into detail into this==

    * `Objects` 

#### Boolean:
#### Null:
 - `null` represents the intentional absence of any object value.
 - `null` is not an identifier for a property of the global object, like `undefined` can be.
 - `null` expresses a lack of identification, indicating that a variable points to no object.
 - `null` is often retrieved in a place where an object can be expected but no object is relevant.

```javascript
/* EXAMPLE-N1: Working with null. Difference between null and undefined, */

typeof null          // "object" (not "null" for legacy reasons)
typeof undefined     // "undefined"
null === undefined   // false
null  == undefined   // true
null === null        // true
null == null         // true
!null                // true
isNaN(1 + null)     // false
isNaN(1 + undefined) // true
```


#### Undefined:

- `undefined` is also property of global `Object`, It is variable in global scope.
- `undefined` is a non-configurable, non-writable property, Even not so don't try to override it.
- A variable that has not been assigned a value is of type `undefined`.
- A function returns `undefined` if a value was not returned.
- It is possible to use it as an `identifier` (variable name) in any scope other than the global scope (because `undefined` is not a reserved word). But, should not do it.

```javascript
/*EXAMPLE-U1: Working with undefined. Different scenarios*/

Object.undefined;                //undefined
undefined;                       //undefined

var x;                           //undefined
typeof x;                        //"undefined"

function func(){                 //undefined, function not returning anything
    var undefined = "foo";       //undefined, as an identifier [x]
    console.log(undefined, typeof undefined);
    //Logs: "foo string"
}

//To check whether some variable has value
if(x === undefined) //This will execute
else //Else, this will execute

//Another way
if(typeof x === undefined) //This will execute
else //Else, this will execute

```

#### Number:

- According to the ECMAScript standard, there is only one number type: the double-precision 64-bit binary format IEEE 754 value (numbers between -(2^53 -1) and 2^53 -1).
- In addition to being able to represent floating-point numbers, the number type has three symbolic values: `+Infinity`, `-Infinity`, and `NaN` (not-a-number).
- All three symbolic values are properties of global `Object`.
- You can also refer `Number` under `Object` Notes for more details[Number Object](./objects).
- The number type has only one integer that has two representations: 0 is represented as -0 and +0.

```javascript

/*EXAMPLE-NUM-2: Workaround: Number datatype in JS*/

// All Symbolic values are properties of global Object

Infinity                            //Infinity
-Infinity                           //-Infinity
NaN                                 //NaN

// Different operations with Infinity
console.log(Infinity          );    //Infinity  
console.log(Infinity + 1      );    //Infinity  
console.log(Math.pow(10, 1000));    //Infinity  
console.log(Math.log(0)       );    //-Infinity  
console.log(1 / Infinity      );    //0 

// Some constants related to Number
Number.MAX_VALUE;                   //1.7976931348623157e+308
Number.MAX_SAFE_INTEGER;            //9007199254740991
Number.MIN_SAFE_INTEGER;            //-9007199254740991

// Two representations of Integer
+0 === -0                           //true
42/+0                               //Infinity
42/-0                               //-Infinity
```


#### String:
    
## Points to ponder:
    
- JavaScript evaluates expressions from left to right. Different sequences can produce different results. _See example-P1_.
- Some behaviour to note about `null` _See example-P2_
- It is possible to use it as an `identifier` (variable name) in any scope other than the global scope (because `undefined` is not a reserved word). But, should not do it. _See example-U1.
    
```javascript
/* EXAMPLE-P1: JS converts number to string when there is operation with string and see how order matters as JS always solves expressions from left to right
*/

    let a = 16 + 4 + "Volvo";         // 20Volvo
    let b = "Volvo" 16 + 4;           // Volvo164
    
/* EXAMPLE-P2: Interesting behaviour of null */

!null               // true
(1 + null)          // 1

/*  */
```