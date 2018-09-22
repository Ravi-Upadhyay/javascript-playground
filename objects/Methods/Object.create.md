# Object.create Method:

- Used to create new object instance.

```javascript

/* SYNTAX: */
Object.create(existing-object);

/* EXAMPLE-1: create new object instance*/

var person1 = {
    fName   : "Ravi",
    lName   : "Upadhyay"
};
var person2 = Object.create(person1);               //{}, new object instance created
person2;                                            //{}
person2.fName;                                      //"Ravi"
person2.fName = "Laxmi";                            //"Laxmi"
person2;                                            //{fName: "Laxmi"}
person2.\_\_proto\_\_;                              //{fName: "Ravi", lName : "Upadhyay"}
```