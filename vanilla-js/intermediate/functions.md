# Functions in JavaScript

```javascript
function name() {
    console.log('hello');
}

// To call a function
name();
```

To use Return Values and Parameters :

```javascript
function name(parameter='default value') {
    return 'Hello ${parameter}' // function ends here. Lines after return are not executed
}

const varName = name('Manan');
console.log(varName);
>'Hello Manan'
```

>[!NOTE]
Functions can also be stored inside variables

```js
const funcVariable = function greeting() {
    console.log('hello');
};

console.log(funcVariable);
>f greeting() { console.log('hello' ) }

console.log(typeof funcVariable);
>function

// To run the function, call the variable
funcVariable();
>'hello'
```

Here, the name of the function is not needed, because the function can be accessed by the name of the variable.  

Such function which has no name is called an Anonymous function.

```js
const funcVariable = function() {
    console.log('hello');
};
```

## Arrow Functions

```js
const funcName = (param1, param2) => {
    console.log('hello');
    return param1 + param2;
}

// To Call it
funcName()
```

### Differences between Normal Functions and Arrow Functions

When an Arrow Function has only one parameter, the () is optional

```js
const oneParam = param1 => {
    console.log(param1);
}
```

When an Arrow Function has only one line, the curly brackets and return statements are optional

```js
const oneLine = () => {
    return 2 + 3;
};

// can be written as
const oneLine = () => 2 + 3; 
```

It is recommended to use Arrow Functions when passing a function as an argument to another function, because it is easier to read.

## 'this' Keyword

**1. Inside a Method, 'this' points to the Outer Object.**
```js
const obj {
    method() {
        console.log(this); // points to obj
    }
}
```

**2. Inside a Function, 'this' is undefined, but we can change it.**
```js
function func(param1, param2) {
    console.log(this);
}

func(); // will return undefined
func.call('hello', 'param1', 'param2'); // will print hello
```

**3. Arrow Functions do not change the value of 'this'.**

>[!IMPORTANT]
**In Arrow functions, 'this' points to the same value it was outside the arrow function.**

```js
const obj = {
    method() {
        console.log(this);

        [1, 2, 3].forEach( function() {console.log(this) } ); // will print undefined we have created a whole new function here, hence we lose access to the outer obj

        // using arrow functions
        [1, 2, 3].forEach( () => {console.log(this) } ); // this points to the obj
    }
}
```