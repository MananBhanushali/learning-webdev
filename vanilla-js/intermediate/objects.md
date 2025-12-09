# Objects in JavaScript

Can be defined as **const/let/var name = { property : value}**  
**Properties of the Object can be accessed by name.property ( Dot Notation ) or name[\'property'] ( Bracket Notation )**

**Bracket Notation is used for properties that cannot be accessed by Dot Notation, or used with variables.**

```javascript
const product = {
    name: 'shoes';
    price: 2000;
}

console.log(product);
>{name: shoes, price: 2000}

console.log(product.name);
>'shoes'

product.name = 'black shoes'; // Properties can also be modified
console.log(product.name);
>'black shoes' 

product['delivery-time'] = 'Tomorrow'; // Since delivery-time cannot be written in Dot Notation. 

// New properties can also be created this way.
product.size = 10;

// To delete a Property
delete product.size;
```

**Shortcut for storing Object Properties in a variable of same name:** 

```javascript
const product = {
    name: 'shoes';
    price: 2000;
}

const name = product.name; // normal way
const price = product.price; 
const { name, price } = product; // shortcut way ( known as destructuring )
```

**Shortcut for storing Object Values from a variable of same name:**
```javascript

const name = 'shoes';
const price = 2000;

const product = {
    name: 'shoes'; // normal way
    price; // shortcut way ( will automatically take the value from price variable ) ( known as Shorthand Property )
}

console.log(product.price);
>2000
```

**Shortcut for creating functions inside objects ( methods ).**
```javascript
const product = {
    method1: function func1() { // normal way
        console.log('Method 1');
    }
    method2() { // shortcut way ( also known as shorthand method )
        console.log('Method 2');
    }
}

product.method1();
>'Method 1'
product.method2();
>'Method 2'
```

**Objects can also be nested (Another Object as Property).**

```javascript
const product = {
    name: 'shirt',
    price: 500,
    rating: {
        stars: 4.5,
        count: 25
    }
}

console.log(product.rating.stars);
>4.5
```

**Functions can also be used as Values of Properties in Objects.**
**Functions inside Objects are called Methods** (ex: console.log(), Math.random() )

```javascript
const funcObject = {
    func: function test() {
        console.log('Inside Function');
        return 'Return Value of Function'
    }
}

funcObject.test();
>'Inside Function'

console.log(funcObject.test()); // Also prints Return Value
>'Inside Function'
>'Return Value of Function'
```

>[!IMPORTANT]
**JavaScript Objects are just references that points to a certain memory location where the data is actually stored.**

**Hence, when an object is created with a const type, the values inside objects can be changed, since only the variable that stores the reference is declared const.**

```javascript
const object1 = {
    name: 'test'
}

object1.name = 'new name';
console.log(object1)
>{
    name: 'new name'
}
```

**Hence, when another object is created which is a copy of the first object,it just copies the reference.And if the first object values are changed,the changes are reflected in the new object too.**

```javascript
const object1 = {
    name: 'test'
}

const object2 = object1;

object1.name = 'new name';
console.log(object2) // same as object1
>{
    name: 'new name'
}
```

**Even if two objects with the exact same properties and values are created separately, they are not equal to each other, since they are different references and point to different memory locations.**

```javascript
const object1 = {
    name: 'test'
}

const object2 = object1;

const object3 = {
    name: 'test'
}

console.log(object3 === object1) // point to different memory locations
>false

console.log(object2 === object1) // point to same memory locations
>true
```