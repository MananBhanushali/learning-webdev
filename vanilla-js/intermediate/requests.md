# Requests and Responses in JavaScript

**Requests** - Message Sent to a Backend URL  
**Response** - Message Received from the Backend in response to the request  

## To Send a Request
```js
const xhr = new XMLHttpRequest();

xhr.open('GET', 'https://url.com/');
xhr.send(); // sends a GET Request to url.com
```
The Request and its response can be viewed in the Network Tab on the Browser

## Obtain The Response in Code
```js
const xhr = new XMLHttpRequest();

xhr.addEventListener('load', () => { // first setup the event listener, then send the message
    console.log(xhr.response);
})

xhr.open('GET', 'https://url.com/');
xhr.send(); // sends a GET Request to url.com
```

## APIs

We can send requests to any route in the base URL which is defined in the backend.  
For ex: /, /hello, /test1, /test2 etc. 

These are called APIs ( Application Programming Interfaces )

The Backend can respond in Text, HTML, Image or JSON format