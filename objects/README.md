# Javascript Objects

The purpose of this module is to put all resources related to JS objects. It will be submodule to Javascript Playground Project. As Objects is very important part of the javascript. 

__//TODO: Not fully updated. Work in progress__

---

## Index:

- Basics
- Classification
- Methods
- Properties
- Object-Oriented javascript
- Prototypes
- Points to ponder
- Resources over web

---

## Basics:
//TODO: Complete this section, read but left due to time crunch follow resources over web section.

### Ways of object creation:

There are four ways of creating an object in javascript. We will see all four approaches here and when we need to use specific approach.

#### 1. Object literal:

- Simplest way of creating an object. Most used approach.
- See __example-wot-1__ for syntax.


```javascript
/* EXAMPLE-WOT-1 Creating new object by literal */

var myObject = {
	name	: 'Ravi',
	age		: '28',
}


```

#### 2. Using constructor (new keyword):

- Another way is to use `new` keyword to create an object from comstructor function.
- This approach is useful when we want to create multiple objects of similar structure/type.

##### 2.1. Object constructor:

- We can use `Object()` constructor to create new `object`.

```javascript

/*EXAMPLE-WOT-2-1 Using Object constructor to create empty object*/

var person1 = new Object();
person1.name = "Chris";
person1['age'] = 38;
person1.greeting = function() {
  alert('Hi! I\'m ' + this.name + '.');
};

/*EXAMPLE-WOT-2-2 Using Object constructor and pass object literal to prefill properties and methods*/

var person1 = new Object({
    name = "Chris",
    age = 38,
    greeting = function() {
        alert('Hi! I\'m ' + this.name + '.');
    }
});

```

##### 2.2. Constructor function:

- As in approach-2.1. we can also create our own constructor to create the objects.
- That constructor will ensure structure of objects that has been created.

```javascript

/* EXAMPLE-WOT-2-3 Creating constructor than creating object instances */

function Human(fName, lName, age){							// This is our constructor function
	this.fName 	= fName;
	this.lName	= lName;
	this.age 	= age;
}

var aScientist = new Human('Albert', 'Einstein', 48);		// This is our object instance created by our constructor

//Human {fName: "Albert", lName: "Einstein", age: "48"}

```

#### 3. Object.create() method:

- JavaScript Object has a built-in method called `create()` that allows you to create instances without creating `constructor`. 
- One major limitation is IE8 doesn't support it.

```javascript

/*EXAMPLE-WOT-3-1 Using Object.create()*/

var person1 = new Object();
person1.name = "Chris";
person1['age'] = 38;
person1.greeting = function() {
  alert('Hi! I\'m ' + this.name + '.');
};

var person2 = Object.create(person1);

```

#### 4. ES6 class: 

- Javascript do not really have a concept of `Class` but it provide us ways to do samething.
- `Class` generally provides structure to create `object instances`.
- We have already seen in approach-2.
- ES6 has introduced sugar syntax to do the same task. See __example-wot-4-1__

```javascript

/* EXAMPLE-WOT-4-1 Creating object using ES6 Class syntax */

class Human {
	constructor(fName, lName, age){
		this.fName = fName;
		this.lName = lName;
		this.age   = age;
	}
}

var me = new Human('Ravi', 'Sharma', 28);

// Human {fName: "Ravi", lName: "Sharma", age: 28}

```

## Classification of Objects:

In javascript everthying except primitive values are objects.

- Booleans can be objects (if defined with the new keyword)
- Numbers can be objects (if defined with the new keyword)
- Strings can be objects (if defined with the new keyword)
- Dates are always objects
- Maths are always objects
- Regular expressions are always objects
- Arrays are always objects
- Functions are always objects
- Objects are always objects

### Number:

- The `Number` JavaScript object is a wrapper object allowing you to work with numerical values. 
- A `Number` object is created using the `Number()` constructor.

//TODO: Due to time crunch, leaving this. Complete by following this link[Number, MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

## Methods:

- The root of all javascript objects is `Object`. In this section we will list methods which `Object` have.
//TODO: Describe Methods: For more details visit [Methods](methods).

## Properties:

- Here we will discuss more about properties in JS.
- Here we will also discuss about properties available to `Object`.
//TODO: Describe Poperties: For more details visit [Properties](properties).

## Object-Oriented javascript:

//TODO:Describe something about javascript, for more follow [Object Oriented Javascript](./object-oriented-javascript)

## Protoypes:

- Javascript often described as `prototype-based language`.
- Each object has a `prototype-object`, which acts as a template object from which it inherits properties and methods.
- An object's prototype object may also have prototype object hence forming `prototype chain`.
- Properties and methods are defined on the `prototype` property on the Objects' constructor functions, not the object instances themselves.
- In JavaScript, a link is made between the object instance and its `prototype` (its `\_\_proto\_\_` property, which is derived from the prototype property on the constructor. 

```javascript

/*EXAMPLE-PRO-1 Passing object literal to create new object and using _proto_ OR getPrototypeOf()*/
var Person = new Object({                   // { name    : "Ravi" }
  name    : "Ravi"                          
});

var Person1 = Object.create(Person);        // {}
Person1.name;                               // "Ravi"
Person1._proto_;                            // { name  : "Ravi" }
Object.getPrototypeOf(Person1);             // { name  : "Ravi" }, recommended way                                         

/* EXAMPLE-PRO-2 Using constructor function */
var Person = function(gender,name,age){
  this.gender = gender;
	this.age    = age;
	this.name	= name;
}


var CEO = new Person('Male', 'Pramod', 32);   // 

// prototype property, You can use prototype to add property/method to constructor function
Person.prototype.getBio = function getBio(){
	console.log('Hi guys I am ' + this.name + 'and I am ' + this.age + 'years old');
}

CEO.getBio();                                 // "Hi guys I am Pramod and I am 32 years old"

Person.prototype;                             // {getBio: f, constructor: f }                      
Person.__proto__;                             // f() { [native code] }      

```

### The prototype property:

- The inherited ones are the ones defined on the `prototype` property (you could call it a sub-namespace).
- The ones that begin with `Object.prototype`., and not the ones that begin with just `Object`.
- The `prototype` property's value is an object, which is basically a bucket for storing properties and methods that we want to be inherited by objects further down the `prototype chain`.
- So `Object.prototype.watch()`, `Object.prototype.valueOf()`, etc., are available to any object types that inherit from `Object.prototype`, including new object instances created.
- `Object.is()`, `Object.keys()`, and other members not defined inside the prototype bucket are not inherited by object instances or object types that inherit from `Object.prototype`. They are methods/properties available just on the` Object()` `constructor` itself.

```javascript

/*EXAMPLE-PRO-3: prototype property*/

// 1: Creating constructor function
var Human = function(gender,age,dob){
	this.gender = gender;
	this.age 	= age;
	this.dob	= dob;
}


// 2: Adding method to prototype 
Human.prototype.isAdult = function(){
	return (this.age >= 18) ? true : false;
}

// 3: Creating object using this constructor

var me = new Human('Male','20', '01/12/1980');

// 4: checking prototype method

me.isAdult();                               //true
Human.isAdult();                            //undefined

```

## Points to ponder:

- When we create an object. Its identifier acts as a pointer only. Potential question for interviews. __See example-pop-1__

```javascript

/* EXAMPLE-POP-1 Javascript object declaration/creation as a pointer only */

var obj = {
	someProp	: 'some value'
}

var anotherObj = obj;

anotherObj.anotherProp = 'another value';

// obj = {someProp : 'some value', anotherProp : 'another value'};
// anotherObj = {someProp : 'some value', anotherProp : 'another value'};

```

## Resources over web:

- [Basics of Objects - Tutorial, MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)
- [Objects, MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [Working with Objects, MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)

