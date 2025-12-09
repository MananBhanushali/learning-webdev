# Arrays in JavaScript

```javascript
const myArray = [10, 20, 30];

console.log(myArray[1]);
>20

myArray[1] = 15; 
console.log(myArray[1]);
>15
```

An Array can have any type of value inside
```javascript
[1, 5, 'hello', { name: 'manan' }, [3, 4]]
```

Array is a special type of object
```javascript
typeof([1, 2]);
>object
```

To check whether an object is an array
```javascript
console.log(Array.isArray([1, 2]));
>true
```

## Properties and Methods of Arrays

1. .length - Gives length of array
2. .push(value) - Adds a value to the end of Array
3. .splice(indexToRemove, numberOfValuesToRemove) - Removes the given number of values at the given index

```javascript
myArray = [10, 20, 30];

console.log(myArray.length);
>3

myArray.push(40); 
console.log(myArray);
>[10, 20, 30, 40]

myArray.splice(1, 2); // Removes 2 values at index 1
console.log(myArray);
>[10, 40]
```

4. .slice() - Copies the values out of an array

>[!NOTE]
Arrays are also references just like objects, hence by adding a value to the copy of an array will add it to the original array too.  

```js
array1 = [1, 2, 3];
array2 = array1; // both are references pointing to the same memory location

array2.push(4);
console.log(array1);
>[1, 2, 3, 4]
```

To overwrite this behaviour, use :
```js
array1 = [1, 2, 3];
array2 = array1.slice(); // The Values of array1 are copied into array2, both are independent arrays

array2.push(4);
console.log(array1);
>[1, 2, 3]

console.log(array2);
>[1, 2, 3, 4]
```

5. **Destructuring**

To get values from an array and store them in variables, destructuring can be used.

```js
const [firstValue, secondValue] = [1, 2, 3];
```

6. **.forEach( function(value, index) )** - Loops through each item of the array and calls the function() with the parameter value ( which is a value in the array ) and index ( which is the index it is currently iterating on )