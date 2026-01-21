# Async and Await in JavaScript

Shortcut for Promises - Even Better way to handle Asynchronous code

**async** - makes a function return a promise

```js
function loadPage() {
    return new Promise((resolve) => {
        console.log('load page');
        resolve('value1');
    })
}

// shortcut for the same code
async function loadPage() {
    console.log('load page');
    return 'value1';
}

loadPage().then((value) => {
    console.log('next step');
    console.log(value);
})
```

**await** - lets us write asynchronous code like normal code 

Instead of using .then(), we can use await to wait for a promise to finish
```js
async function loadPage() {
    console.log('load page');
    const value = await fetchData(); // the returned value can be saved in a variable
    console.log('page fetched'); // will run after fetchData() promise is resolved
}
```

await can only be used inside an async function ( incase of nesting, the closest function needs to be async )

### Error Handling - try / catch
To catch errors in async await, try-catch can be used

```js
try {
    async function loadPage() {
        const value = await fetchData();
        console.log('page fetched');
    }
} catch (error) {
    console.log('Unexpected Error. Please try again');
    console.log(error);
}
```

When we get an error, it skips the code below that point and moves directly to the catch block.

We can also manually create errors using **throw**
```js
try {
    throw 'error1';
} catch (error) {
    console.log(error); // will print error1
}
```

To create error in a Promise ( in the future ), we use **reject()**
```js
new Promise((resolve, reject) => {
    fetchData(() => {
        reject('error1');
    })
})
```