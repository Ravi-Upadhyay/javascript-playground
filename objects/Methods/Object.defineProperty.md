# defineProperty Method:

- Precisely defines new property directly onto object or modifies existing property.
- Call this method on `Object constructor` rather than on `instance` of Object.
- It returns the object.

### Description:
- Normal property addition through assignment creates properties which (1) show up during property enumeration (for...in loop or Object.keys method), (2) whose values may be changed, and (3) which may be deleted. 
- This method allows these extra details to be changed from default.
- Property descriptors have two flavours
    - **Data descriptors:**  Is a property that has a value, which may or may not be writable.
    - **Accessor descriptors:** Is a property described by getter-setter pair  of functions.
- Please visit [property](../properties) for more details about this.
- `Object.freeze()` can be used to freeze objects as writable will not affect objects.[freeze()](Object.freeze.md).
- `{configurable : false}` generally has these affects on the property
    - Unable to set `enumerable` for that property. However, you still can set `writable`.
    - Unable to delete that property.
- Getters-Setters are provide us a way to define properties to get or set some value.

### Syntax:

```javascript

Object.defineProperty(obj, prop, descriptor);

```

### Example:

```javascript

/* EXAMPLE-DP-1 Make property of object not writable */

var obj = {
    prop    : 'someValue'
};

Object.defineProperty(obj, prop, {
    writable    : false
});

obj.prop = 'anotherValue';                          // 'someValue', it will not changed. If in strict mode it 
                                                    // will through error.

// If property is pointing to another object.

var obj = {
    prop    : {
        nProp   : 'someValue'
    }
};

Object.defineProperty(obj, 'prop', {
    writable    : false
});

obj.prop.nProp = 'anotherValue';                    // 'anotherValue', because here prop is nothing but pointer.

// However, we can do this by
Object.freeze(obj.prop);


/* EXAMPLE-DP-2 Make property of object not enumerable */

var obj = {
    fName       : 'Ravi',
    lName       : 'Sharma'
};

for (var prop in obj){
    console.log(`${prop}: ${obj[prop]}`);
}                                                  

// fName    : Ravi
// lName    : Sharma

Object.defineProperty(obj , lName, {
    enumerable  : false
});

// fName    : Ravi

/* EXAMPLE-DP-3 Make property non-configurable */

var obj = {
    fName       : 'Ravi',
    lName       : 'Sharma'
};

Object.defineProperty(obj, 'lName', {
    configurable    : false
});

Object.defineProperty(obj, 'lName', {
	enumerable	: false
});                                                             // Uncaught TypeError: cannot redefine property

Object.defineProperty(obj, 'lName', {
    writable    : false
});                                                             // Writable can be changed

delete obj.lName;                                               // false, cannot delete because it has configurable = false

/* EXAMPLE-DP-4 Getter and Setter */

var obj = {
    fName       : 'Ravi',
    lName       : 'Sharma'
};

Object.defineProperty(obj, 'fullName', {
	get	: function(){
		return this.fName + ' ' + this.lName;
	},
	set : function(value){
		var nameParts = value.split(' ');
		this.fName = nameParts[0];
		this.lName = nameParts[1];
	}
});

obj.fullName;                                                   // "Ravi Upadhyay"
obj.fullName = "Kavi Verma"                                     // "Kavi Verma"
obj;                                                            // {fName: "Kavi", lName: "Verma"}

```