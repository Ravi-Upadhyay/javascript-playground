### Callback Functions - Argument Passing

We have seen example of simple/general callback function [here](callback-functions.md). However, there are 
some cases where we have some other requirements too. 

```
//FUNCTION-1: Definition, Supposed to be a callback function
function callbackFunction() {
  console.log(`Hello I am callback function`);
}

//FUNCTION-2: Definition, Callback function as argument and will be executed
function generalFunction(callback){
  
  //Do something
  //Call/Execute Callback
  callback();
}

//EXECUTE:
generalFunction(callbackFunction)

```