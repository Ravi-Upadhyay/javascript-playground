# Javascript Objects

The purpose of this module is to put all resources related to JS objects. It will be submodule to Javascript Playground Project. As Objects is very important part of the javascript. 

> 

__//TODO: Only template is there for now. Keep adding related content__

---

## Index:

- Basics
- Classification
- Methods
- Properties
- Object-Oriented javascript
- Prototypes
- Resources over web

---

## Basics:
//TODO: Complete this section, read but left due to time crunch follow resources over web section.

### Ways of object creation:

#### 1. Object literal:

#### 2. Constructor function:

#### 3. Object constructor:

We can use `Object()` constructor to create new `object`.

```javascript

/*EXAMPLE-WOT-3-1 Using Object constructor to create empty object*/

var person1 = new Object();
person1.name = "Chris";
person1['age'] = 38;
person1.greeting = function() {
  alert('Hi! I\'m ' + this.name + '.');
};

/*EXAMPLE-WOT-3-2 Using Object constructor and pass object literal to prefill properties and methods*/

var person1 = new Object({
    name = "Chris",
    age = 38,
    greeting = function() {
        alert('Hi! I\'m ' + this.name + '.');
    }
});

```

#### 4. Object.create() method:

JavaScript has a built-in method called `create()` that allows you to create instances without creating `constructor`. One major limitation is IE8 doesn't support it.

```javascript

/*EXAMPLE-WOT-3-4 Using Object.create()*/

var person1 = new Object();
person1.name = "Chris";
person1['age'] = 38;
person1.greeting = function() {
  alert('Hi! I\'m ' + this.name + '.');
};

var person2 = Object.create(person1);

```

## Classification:

### Number:

- The `Number` JavaScript object is a wrapper object allowing you to work with numerical values. 
- A `Number` object is created using the `Number()` constructor.

//TODO: Due to time crunch, leaving this. Complete by following this link[Number, MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

## Methods:

//TODO: Describe Methods: For more details visit [Methods](methods).

## Properties:

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
/* Human

ƒ (gender,age,dob){
	this.gender = gender;
	this.age 	= age;
	this.dob	= dob;
}
*/

// 2: Adding method to prototype 
Human.prototype.isAdult = function(){
	return (this.age >= 18) ? true : false;
}

/* Human

ƒ (gender,age,dob){
	this.gender = gender;
	this.age 	= age;
	this.dob	= dob;
}
*/

/* Human.prototype.isAdult

ƒ (){
	return (this.age >= 18) ? true : false;
}
*/

// 3: Creating object using this constructor

var me = new Human('Male','20', '01/12/1980');

// 4: checking prototype method

me.isAdult();                               //true
Human.isAdult();                            //undefined

```

## Resources over web:

- [Basics of Objects - Tutorial, MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)
- [Objects, MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [Working with Objects, MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)

