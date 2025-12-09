# Document Object Model ( DOM ) in JavaScript

The DOM combines HTML and JavaScript together, and hence gives JavaScript control over HTML

**Properties and Methods of document Object:**

```javascript
document.title = 'title';

// document.body contains: <body>...</body>
// typeof document.body returns object. Hence it is an object and has its own properties and methods

document.body.innerHTML = '<button>hello</button>'; // document.body.innerHTML gives all inner HTML, which can also be changed

console.log(document.querySelector('button')); // will return the first button element from the page
><button>hello</button> 
```

**Every Element has .innerHTML property , which can be used to view and edit its content.**

**To view the Inner Text, use the .innerText property.**

```javascript

document.body.innerHTML = '<button>hello</button>';

console.log(document.querySelector('button').innerText);
>hello

document.querySelector('button').innerText = 'changed'

console.log(document.querySelector('button').innerText);
>changed
```

>[!IMPORTANT]
To look for a particular element, assign it a class, and then use: **document.querySelector('.className')**

```javascript

document.body.innerHTML = `
<button class='first-button'>First</button>
<button class='second-button'>Second</button>
`;

console.log(document.querySelector('.second-button').innerHTML);
>Second
```

**element.classList.add('class-name') and element.classList.remove('class-name') can be used to add / remove classes from an element.**

**This can be used to change the appearance of an element on click, by giving it another class onclick, and then styling that class accordingly.**

## Timeouts and Intervals

### setTimeout(func, time)

Will run the function after the given time (in ms).  
Till then the next code will run ( Due to the Asynchronous Nature of JavaScript )

```js
setTimeout(function greeting() {
     console.log('hello');
     }, 3000); // will run after 3 seconds ( 3000 milliseconds )
```

### setInterval(func, interval)

Will run the function every interval ( multiple times ). 

**setInterval() returns a number ( an id ) which can be used to later stop the interval using clearInterval(ID).**

```js
const intervalID = setInterval(function greeting() {
     console.log('hello');
     }, 3000); // will run after every 3 seconds ( 3000 milliseconds )

clearInterval(intervalID);
```

## Event Listeners

```js
element.addEventListener(event, funcName);

// To Remove an Event Listener 
element.removeEventListener(event, funcName);
```

For Example :

```js
const buttonElement = document.querySelector('.button-classname');

const func = () => {
    console.log('Click Registered');
};

buttonElement.addEventListener('click', func);

buttonElement.removeEventListener('click', func);
```