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
