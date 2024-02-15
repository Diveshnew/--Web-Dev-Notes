# Ultimate-Web-Dev-Notes

## Full Stack Web Dev RoadMap
## 1. How Programming Works?
```
    C & C++
        - Procedural Programming
        - Functions
        - Pointers      
    Java
        - OOPS
        - Design Principles
        - Design Patterns
```

## 2. Basics
```
How Internet Works?
What is a website?
Basics of DNS
```

## 3. Getting Started with WebDev
```
    HTML & CSS
        - Build 10-20 Static Good Looking Websites
        
    CSS Libraries
        - BootStrap

    JavaScript
        - Build 10-20 Functional Web Applications
          ( Todo, Weather API , Tic Tac Toe Game )
```

## 4. Server Side

### `Understanding`
```
What is a Webserver?
What is Req Res Cycle
What is Rest API
What are server Rendered
Linux Fundamentals
```

### `Server Side Programming (Node JS)`
```
How Node Works
Modules and Packages
Express FrameWork
Building & Testing REST API's With Express
Building API's and Connecting them with FrontEnd application using HTML CSS Javascript
Server Side Rendering ---> EJS
```

### `Databases`
```
MongoDB (Popular)
Firebase Firestore (Fast and Realtime)
PostgresQL (For SQL Usercases)
```

### `Auth`
```
Cookies
Tokens
Protected Routes
```

### `API Building`
```
API's with Full CRUD functionality
```

## 5. FrontEnd

### `Choose A FrameWork`
```
Angular
Vue
React (Most Popular)
    - What is React?
    - Components
    - Hooks
    - State Management
    - Life Cycle Events
    - State Management using Redux
    * API Calling
          - Fetch
          - RTK Query
          - React Query
```

## 6. Basics of Cloud and Deployments
```
Deploy with Heroku

AWS
  - Ec2
  - Load Balancer
  - Cloud Front
  - Serverless
        - Lanbda Functions
        - API Gateway
```

## 7. Build A Full Stack Application - MERN ( MongoDB, Express, React, Node)
```
Social Media
E-commerce
Blogging
```

## 8. UpSkill Yourself
```
TYPESCRIPT

Server
    - Graphql
    - Socket Programming
    - Redis

Client ----> Next JS
                  - CSR
                  - SSR
                  - SSG
```


## Javascript Notes

### Prototype Chain
How does Prototypal Inheritance work?

Prototype Chain
The prototype chain is a mechanism that allows objects to inherit properties and methods from other objects. Every object can have exactly one prototype object. That prototype object can also have a prototype object, and so on, creating a chain of inheritied properties and methods. The end of this chain is called the null prototype.

In general, you don’t need to think about the prototype chain when doing everyday JavaScript development. However, it is important to understand how it works because it’s the basis for the class keyword and essential knowledge as you dive deeper into the language.

In the example below, we see how an dog can inherit properties from the animal object, which itself inherits properties from the root Object.prototype.

```Javascript
const animal = {
  dna: 'ATCG',
};

const dog = {
  face: '🐺',
}

Object.setPrototypeOf(dog, animal);

Object.getPrototypeOf(dog) === animal; // true

Object.getPrototypeOf(animal) === Object.prototype; // true

Object.getPrototypeOf(Object.prototype) === null; // true
```

### Destructuring
Use destructuring to work with objects with ease.

Destructuring Examples
```Javascript
// Object destructuring
const person = {
  name: 'John',
  age: 32,
  city: 'New York',
  country: 'USA'
};

const { name, age } = person;

// Object destructuring with alias

const { name: firstName, age: years } = person;

// Array destructuring
const fruits = ['apple', 'banana', 'orange'];
const [first, second, third] = fruits;
```

### Spread
Use the spread syntax to combine objects

Spread Syntax
The spread syntax ... is a relatively new operator that was introduced in ES2018. It provides a concise way to combine objects and arrays.
```Javascript
const obj = { 
    foo: 1, 
    bar: 2, 
    baz: 3 
};
const newObj = {
    foo: 4
    ...obj,
};
console.log(newObj); // { foo: 1, bar: 2, baz: 3 }
```
It’s also useful for combining arrays.

```Javascript
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [...arr1, ...arr2];
```

### Optional Chaining
Call object properties safely

Optional Chaining
Optional chaining ? is a relatively new operator that was introduced in ES2020. It allows you to call object properties safely, without throwing an error. When calling properties without this operator, you many crash your applcation with the error Cannot read property 'foo' of undefined.

```Javascript
const person = { };

const dude = person.name;
console.log(foo); // Uncaught TypeError: Cannot read property 'bar' of undefined

const dude = person?.name; // undefined
```

### Nullish Coalescing
How nullish coalescing is realted to truthy and falsy values

Nullish Coalescing
Nullish coalescing is a relativly new operator that was introduced in ES2020. It is similar to the logical OR operator ||, but it only returns the right-hand side if the left-hand side is null or undefined.

```Javascript
const foo = null ?? 'bar';
console.log(foo); // 'bar'

const foo = 0 ?? 'bar';
console.log(foo); // 0
```

### Higher Order Functions
What is a higer order function or HOF?

Higher Order Functions
A higher order function is a function that takes a function as an argument, or returns a function. They are commonly used in functional programming, and are a powerful tool for abstracting away complexity.
```Javascript
// A function that takes a function as an argument
function add(x, y) {
  return x + y;
}
function subtract(x, y) {
  return x - y;
}
function math(x, y, operator) {
  return operator(x, y);
}

math(5, 2, add); // 7
```

### Closures
A closure is a function that has access to the parent scope, even after the parent function has closed. JS will automatically store the state of a closure in the heap memory, even after the parent function has returned. This behavior makes them useful for encapsulating private variables.
```Javascript
function encapsulatedState(x) {
  let state = 10;
  return function() {
    state += x;
    return state;
  }
}
```

### Array Tricks
Useful techniques for working with JS arrays

Create a Range of Numbers
```Javascript
const range = Array(100).fill(0).map((_, i) => i + 1);

// OR

const range = [...Array(100).keys()];
```

Remove Duplicates from an Array
```Javascript
const unique = [...new Set(arr)];
```

Get a Random Element
```Javascript
const random = arr[Math.floor(Math.random() * arr.length)];
```

Loop over a Key-Value Pair
```Javascript
for(const [i, val] of arr.entries()) {
    console.log(i, val);
}
```

Homework: Array Methods to Study
```Javascript
arr.forEach();
arr.map()
arr.filter();
arr.find();
arr.findIndex();
arr.reduce();
```

### History of JavaScript
How JavaScript evolved into the language we know today

History of JavaScript
Read the full Weird History of JavaScript article.


## Algorithms

### Cumulative Sum
Solving basic algorithms with plain JavaScript

Cumulative Sum Interview Question
Create a function that takes an array of numbers and returns a number that is the sum of all values in the array.

Cumulative Sum Implementation
```Javascript
// Solution 1
function cumSum(arr) {
    return arr.reduce((acc, cur) => acc + cur, 0);
}

// Solution 2
export function cumSum(arr) {
  let total = 0;
  
  for(let i = 0; i < arr.length; i++) {
    total += arr[i];
  } 
  
  return total;
}

console.log('sum: ', cumSum([1,3,5,7]));

```

###  Binary Search
How to implement binary search in JavaScript

Binary search is a faster way to find an item in a sorted array with O(log n) time complexity, compared to a regular loop with O(n) time complexity.

Binary Search Interview Question
Create a function that takes a sorted array and a target value. Return the index of the target value in the array. If the target value is not in the array, return -1.

Binary Search Implementation
```Javascript
function search(arr, target, start=0, end=arr.length-1) {

    console.log(start, end)

    if (start > end) {
        console.log('Not found!');
        return -1;
    } 

    const middle = Math.floor( (start + end) / 2 );

    if (arr[middle] === target) {
        console.log(`${target} Found at index ${middle}`);
        return middle;
    } 

    if(arr[middle] > target) {
        return search(arr, target, start, middle-1);
    }

    if(arr[middle] < target) {
        return search(arr, target, middle+1, end);
    }

}

const arr = ['a', 'b', 'c', 'x', 'y', 'z'];
console.log(search(arr, 'b'));
```

### Least Recently Used (LRU) Cache
How to implement an LRU cache in JavaScript

The LRU cache is one of the most commoly asked algorithm questions on interviews.

LRU Interview Question
Create a data structure that implements the requirements of a Least Recently Used (LRU) cache with O(1) average time complexity.

Initialize an object with a maxium capacity of elements.
getItem Return the value of the key. Update cache with the most recently used key.
putItem Create or update a key value pair in the cache. Evict the least recently used key if the size of keys exceeds the max capacity.
LRU Implementation in JavaScript
```Javascript
export class LRU {
  constructor(capacity) {
    this.capacity = capacity;
    this.cache = new Map();
  }

  getItem(key) {
    const item = this.cache.get(key);

    // Map keeps track of insertion order, this will refresh the item
    if (item) {
      this.cache.delete(key);
      this.cache.set(key, item);
    }
    return item;
  }

  putItem(key, val) {
    // delete to refresh the insertion order
    if (this.cache.has(key)) {
      this.cache.delete(key);
    }
    // evict the oldest item in the cache
    else if (this.cache.size == this.capacity) {
      this.cache.delete(this.oldestItem);
    }

    this.cache.set(key, val);
  }

  get oldestItem() {
    return this.cache.keys().next().value;
  }
}

const cache = new LRU(5);
cache.putItem('a', 1);
cache.getItem('a');
```

###  TDD with Vitest
How to test JavaScript code with Vitest

Use Vitest to create a few basic unit test for the algorithims in the previous lessons.
```Javascript
npm init -y
npm i -D vitest
```

Update the package.json with a test script.
```package.json
 "scripts": {
    "test": "vitest"
  },
```

Vitest Basic Example
```javascript
import { expect, test } from 'vitest';

import { cumSum } from './sum';
test('cumulative sum of an array', () => {
  expect(cumSum([1, 3, 5, 7])).toBe(16);
  expect(cumSum([-2, -4, -8])).toBe(-14);
});
```
