# Check for Properties

The purpose of this document is to see how we can check for `properties` in `object`. One such check may be whether the `property` exists or not. There may be many things which may come across via different blogs and other sources. 

## Check if property exists

Sometimes, it may be very useful to check whether an `object` have particular `property` or not. This may help in writing bug free code.

1. __Using `Object` prototype:__

Every object has `prototype` of global `Object`. `Object` has one method called `hasOwnProperty()`. We can utilize this method to  check whether property exists or not.

```
//Sample Object

var myObject = {
	firstProperty: 'value-1',
	secondProperty: {
		firstSubProp: 'sub value-1'
	}
};

// Output will be: true
myObject.hasOwnProperty('firstProperty');
```

2. __Using `in`:__

One way which I came across in some documentation is using `in` keyword.

```
//Sample Object

var myObject = {
	firstProperty: 'value-1',
	secondProperty: {
		firstSubProp: 'sub value-1'
	}
};

// Output will be: 'property found'
if('firstProperty' in myObject) console.log('property found');
```