# Storing Data In JavaScript

- [Storing Data In JavaScript](#storing-data-in-javascript)
  - [JSON ( JavaScript Object Notation )](#json--javascript-object-notation-)
  - [Local Storage](#local-storage)


## JSON ( JavaScript Object Notation )

Difference between JavaScript Objects and JSON:
- JSON cannot store Functions
- In JSON, all the property names and values should be in double quotes.

To Convert JavaScript Object to JSON string: use **JSON.stringify(object)**
To Convert JSON string into JavaScript Object: use **JSON.parse(string)**

```javascript
const testObject = {
    name: 'test';
    price: 100;
    func: function test() {
        console.log('Function');
    }
}

const jsonString = JSON.stringify(testObject);
console.log(jsonString);
>{
    "name": "test", "price": 100
} // Function not present in JSON   

console.log(typeof jsonString);
>string

const newObject = JSON.parse(jsonString); // will not have function test()
```

## Local Storage 

To set Data in Local Storage: use **localStorage.setItem('\<name>', '\<value>')** ( only supports strings )

To get Data from Local Storage: use **localStorage.getItem('\<name>')**

To remove Data from Local Storage: use **localStorage.remove('\<name>')**

```javascript
localStorage.setItem('message', 'hello');

console.log(localStorage.getItem('message'));
>'hello'

localStorage.remove('message');
```