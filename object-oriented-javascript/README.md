# Object-Oriented javascript:

Object-oriented JavaScript (OOJS) — this article presents a basic view of object-oriented programming (OOP) theory, then explores how JavaScript emulates object classes via constructor functions, and how to create object instances.

## Index:

- Basics of object-oriented programming
- 

## Basics of object-oriented programming:

- The basic idea of OOP is that we use objects to model real world things that we want to represent inside our programs.
- `Object` data (and often, functions too) can be stored neatly (the official word is `encapsulated`) inside an object package (which can be given a specific name to refer to, which is sometimes called a `namespace`).
- When an `object` instance is created from a `class`, the `class`'s `constructor` function is run to create it. This process of creating an object instance from a class is called `instantiation` — the object instance is instantiated from the `class`.
- In OOP, we can create new classes based on other classes — these new `child` classes can be made to inherit the data and code features of their `parent` class

### Constructors and object instances:

- JavaScript uses special functions called `constructor` functions to define objects and their features.
- Constructors provide the means to create as many objects as you need in an effective way, attaching data and functions to them as required.
- We can have this with normal function _See example-con-1_. But, we know we want to create an object, why do we need to explicitly create a new empty object and return it? 
- Solution is `constructor` function. _See example-con-2_. It has all the features you'd expect in a function, although it doesn't return anything or explicitly create an object.
-  A `constructor` function name usually starts with a capital letter — this convention is used to make `constructor` functions easier to recognize in code.
- Note that when we are calling our constructor function, we are defining greeting() every time, which isn't ideal. To avoid this, we can define functions on the prototype instead.

```javascript

/*EXAMPLE-CON-1 Construction of Objects with Normal function*/

function createNewPerson(name){
    var person = {};
    person.name = name;
    person.greeting = function() {
        alert('Hi I am ' + this.name);
    };
    return person;
}

// Create new person by calling this function
var salva = createNewPerson('Salva');
salva.name;                             //"Salva"
salva.greeting();                       //"Hi I am Salva"

/*EXAMPLE-CON-2 Using constructor function*/
function Person(name){
    this.name = name;
    this.greeting = function() {
        alert('Hi I am ' + this.name);
    };
}

//Creating new person
var salva = new Person('Salva');
```