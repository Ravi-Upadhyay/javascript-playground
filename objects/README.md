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

## Resources over web:

- [Basics of Objects - Tutorial, MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)
- [Objects, MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [Working with Objects, MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)

