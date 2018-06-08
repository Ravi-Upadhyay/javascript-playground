# Javascript - Callback Functions

A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action. 

In javascript functions are first-class objects, functions are of the type `Object`. So they can be passed as arguments, can be created inside another functions, and can be returned from another function. 

This mysterious behaviour of functions is essence of callback functions. Yet it is most widely used functional programming techinique in javascript. It can be called callback pattern as well.

## Index - How things will progress

1. A simple callback function.


### General Example

Here is general example of callback function. This is `synchronous` function call however callbacks most often used with `asynchronous` function call.

```
//FUNCTION-1 DEFINITION
function greeting(name) {
  alert('Hello ' + name);
}

// FUNCTION-2 DEFINITION, It will receive FUNCTION-1 as argument and execute it.
function processUserInput(callback) {
  var name = prompt('Please enter your name.');
  callback(name);
}

//FUNCTION-1 has been sent argument to the FUNCTION-2
processUserInput(greeting);

```

### How to put gloominess away

There so many gloomy things which revloves around. We will list such things here with example.

1. [Passing arguments to callback function](callback-arguments-passing.md)
2. [Confusion about `this`](callback-this-explained.md)

