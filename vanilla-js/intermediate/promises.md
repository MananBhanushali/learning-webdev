# Promises and Fetch in JavaScript

## Promises - Better way to handle asynchronous code  
Let's us wait for some code to finish, before going to the next step

Promises are defined as a Class. So to create a Promise
```js
new Promise(() => { 
    console.log('promise'); // runs immediately
})
```

The inner function inside the promise runs immediately

The inner function can have an argument **resolve** which is used to handle asynchronous code

```js
new Promise((resolve) => { 
    asyncFunc(() => {
        resolve();
    });
})
```

We run some asynchronous code ( asyncFunc ), wait for it to finish, and then call resolve to go to the next step.

To add a next step, we use the **.then()** function

```js
new Promise((resolve) => { 
    asyncFunc(() => {
        resolve();
    });
}).then(() => {
    console.log('next step');
})
```

resolve() lets us control when to go to the next step. The .then() function is called only after the promise is resolved

We can also pass arguments to resolve, and add parameters in the .then() function

```js
new Promise((resolve) => { 
    asyncFunc(() => {
        resolve('value1');
    });
}).then((value) => {
    console.log(value);
})
```

To use multiple Promises, nesting can be done. **Promise.all()** can be used to wait for multiple promises to resolve for a single next step.  
It accepts an array of multiple promises.

All the promises run at the same time, instead of one by one
```js
Promise.all([
    new Promise((resolve) => { 
        asyncFunc(() => {
            resolve('value1');
        });
    }),
    new Promise((resolve) => { 
        asyncFunc2(() => {
            resolve('value2');
        });
    })
]).then((values) => {
    console.log(values); // array of values (value1 and value2)
})
```

Also, inside the .then() function, another promise can be returned, and another .then() can be used which will run when that promise is resolved.

## fetch() - Better way to make HTTP requests
```js
fetch('https://url.com/') // default method is GET
```

fetch() returns a promise, which is resolved when the response is received. 
The response is also saved as an argument ( can be accessed from .then() )

```js
fetch('https://url.com/').then( (response) => {
    console.log(response)
})
```

We can also use requests other than GET
```js
fetch('https://url.com/', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        data: 'my-data'
    })
})
```
headers gives the backend more information about our request
body contains the actual data to send ( in this case , json format)

### Error handling in Promises - .catch()

```js
const promise = fetch('https://error.url.com/').then((response) => {
    return response.json();
}).catch((error) => {
    console.log('Unexpected Error. Please try again');
    console.log(error);
})
```