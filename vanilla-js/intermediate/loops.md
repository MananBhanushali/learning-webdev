# Loops in JavaScript

## While Loop

```js
while (condition) {
    body
    increment step
}
```

For Ex:

```js
let i = 1;

while ( i<=5 ) { // will run 5 times
    console.log(i);
    i++;
}
```

## For Loops

```js
for (loop-variable, condition, increment) {
    body
}
```

## break and continue

break - Used to stop the loop early
continue - used to skip an iteration, and move on to the next

```js
for ( let i=1, i<=10, i++ ) { // prints all from 1 to 10

    if ( i=5 ) {
        continue; // when i=5, the iteration will end here and move on to i=6, hence 5 will not be printed
    }

    console.log(i) 

    if ( i=8 ) {
        break; // when i=8, loop will end and hence only numbers till 8 will be printed ( excluding 5 )
    }

}
```
