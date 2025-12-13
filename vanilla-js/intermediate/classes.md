# Classes in JavaScript

Classes are Object Generators

For Example,
```js
obj1 = {
    property1: 'abc';
    property2: 'def';

    method1() {
        console.log(property1);
    }
}

// now if we want to create another obj with the same properties / methods, we will have to copy the code.

obj2 = {
    property1: 'abc';
    property2: 'def';

    method1() {
        console.log(property1);
    }
}
```

By using Classes, we can create a Blueprint Object, and then create as many objects as we want

**The 'this' keyword can be used to access the properties ( fields ) of the class from the class methods**

```js
class Obj {
    property1: undefined;
    property2: 'def';

    method1() {
        console.log(this.property1);
    }
}

// to create an Obj 
const obj1 = new Obj();
obj1.property1 = "first object";
console.log(obj1.method1())

const obj2 = new Obj();
obj1.property1 = "second object";
console.log(obj2.method1())
```

**Objects created with a Class are known as Instances of that Class.**

To Check if an object is an instance of a class
```js
console.log(obj1 instanceof Obj) // returns true or false
```

## Constructors

**The Constructor is a Special Function that is run when an Object is created.**  
**The Constructor can be given parameters, which accept value from the user when the Object is created.**  

```js
class Obj {
    property1;
    
    constructor(property1) {
        this.property1 = property1; // assigns the user-given argument to the class property
        this.method1(); // will run method1 on object creation
    }

    method1() {
        console.log(this.property1);
    }
}

const obj1 = new Obj("hello");

obj1.property1 = "changed"; // property1 is still accessible from outside the class
obj1.method1();
```

>[!NOTE]
A Constructor function should have no return value.

## Private Properties and Methods

In the previous code, the properties and methods of the object can be accessed and modified outside from outside the object. To Prevent this, We can make them private

**To make any property/method private, just add '#' in front of it.**   

```js
class Obj {
    #property1;
    
    constructor(property1) {
        this.#property1 = property1;
        this.#method1();
    }

    #method1() {
        console.log(this.#property1);
    }
}

const obj1 = new Obj("hello");

// will not work
obj1.#property1 = "changed";
obj1.#method1();
```