# Inheritance in JavaScript

A Class can inherit all the properties/methods of another Class and add its custom properties/methods to it. This is called Inheritance.

The Original Class is called the Base Class or Parent Class, and the Class which inherits it is called the Derived Class or Child Class.

```js
class Base {
    baseProperty1;

    constructor(property1) {
        this.baseProperty1 = property1;
    }

    baseMethod1() {
        console.log(this.baseProperty1);
    }
}

class Derived extends Base { // inherits all properties/methods of the base class including the constructor

}

const derivedObj = new Derived("This is the Derived Class.");
```

## Constructor in Inheritance

**The Derived Class by default inherits the Base Class Constructor if it is not defined.**

If the Derived Class Constructor is defined, the **super()** keyword along with the required arguments can be used to call the Base Class Constructor, and then the additional code of Derived Class Constructor can be added.

```js
class Base {
    baseProperty1;

    constructor(property1) {
        this.baseProperty1 = property1;
    }

    baseMethod1() {
        console.log(this.baseProperty1);
    }
}

class Derived extends Base { 
    derivedProperty;

    constructor(property1, property2) {
        super(property1); // run the Base Class Constructor with property1 argument
        this.derivedProperty = property2;
    }
}

const derivedObj = new Derived("This is the Derived Class.");
```

>[!IMPORTANT]
**super.methodName() can be used to use any method/property from the Base Class.**

