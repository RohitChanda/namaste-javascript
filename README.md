# Core Concept of JavaScript


## 🚀 Execution Context:
- Everything in JavaScript happens inside an execution context.
- You can assume that this execution context is a big box of containers in which the whole javascript code is executed.
- It has two components. ( 1.**Memory Component** , 2.**Code Component**)                                                                                  

| Memory Component       | Code Component    |
|------------------------|---------------|
| Here all variables and functions are stored as a key-value pair. <br/> Key:  value, <br/> A: 10, <br/>  Fn: {...}  | The whole code is executed one line at a time. |
| It is also known as the Variable Environment                                                                       | It is also known as the Thread of execution |


### How is this execution Context created?
```js
1.var n = 2;
2.function square(num) {
3.    var ans = num * num;
4.    return ans;
5.}
6.var sqaure2 = square(n); // function invoke
7.var sqaure3 = square(4); // function invoke
```
When the whole code is running behind the scenes a global execution context is created. It creates two phases.
- **Memory creation phase( 1st phase)**.
- **Code Execution phase(2nd phase)**.

![image](https://github.com/user-attachments/assets/0e2b13d7-af10-404b-b73b-a4efa4dcc3d3)

#### call stack
![image](https://github.com/user-attachments/assets/22b39b06-9ec3-4ae8-9bf7-d34dc9af4211)

- At the bottom of the stack, we have the Global Execution Context.
- Whenever a js program runs, the call stack is populated with a Global execution context.
- When a new execution context is created suppose e1, it is pushed into the stack.
- When e1 is done and returned, this e1 is moved out from the stack, and from the next line e2 is pushed into the call stack

Call Stack maintains the order of execution of the execution context.

The call stack is also known as →
- Execution Context stack
- Program Stack
- Control stack
- Runtime Stack
- Machine Stack

## 🚀 Hoisting in JavaScript

Hoisting is a feature in JavaScript by which you can access variables and functions even before initializing it or putting some value in it. And you can access it without any error.

![image](https://github.com/user-attachments/assets/09af16ee-58cc-4535-b1ba-2b7c2c668c86)

<img width="469" alt="image" src="https://github.com/user-attachments/assets/93f9c7be-1663-413c-bbb8-543bf977a6ac">

### Explain this code

<img width="469" alt="image" src="https://github.com/user-attachments/assets/e47a32f4-f231-4766-a3eb-b551a82d3f78">

***Explanation***

In Execution Context : 

<img width="500" alt="image" src="https://github.com/user-attachments/assets/8de164f7-47a7-44dc-b1b2-54801d1adebb">



## Q> Is var Allow Redeclarations?
yes.

<img width="480" alt="image" src="https://github.com/user-attachments/assets/3d2e345f-1bcf-4f57-a3e2-4e6ee4f843de">


## Q> What is the shortest js program?
- An empty js file.
- Even though a file is empty JavaScript creates a Global execution context and also sets something in the memory space.
- At the top/global level, this points to the window object.


## Q> Difference b/w undefined and not-defined?
**undefined**: It means it is present in the memory but not assigned any value.
**not-defined**: It not present in the memory.



## 🚀 Scope

### Q> What is the scope? 
Where you can access specific variables and function in our code. Scope is directly dependent on the lexical environment.

### Q> What does Scope of a variable means? 

### Q> Is b inside the scope of a function?


## 🚀 Lexical Environment

### Q> What is the Lexical Environment?
It is the local memory along with the Lexical Environment of Parent.

<img width="472" alt="image" src="https://github.com/user-attachments/assets/b3fdfcda-525e-491b-985f-2c1bfa01d908">
<br/>

<img width="473" alt="image" src="https://github.com/user-attachments/assets/ccdccce0-9478-44fa-931d-70e9259401e8">


## 🚀 Let and const in js:
- let and const are hoisted but they are hoisted very differently than var.
- let and const not stored in Global Object like var.

  <img width="440" alt="image" src="https://github.com/user-attachments/assets/1a5c7115-80e0-47d8-94e4-0c839da8c87b">

- Even before a single line of code executed , we can see javascript allocated a memory for **a** in **Script memory** object but **not assigned any value**.But in case var is assigned **undefined** to it.
- We can't access these let and const declarations before putting some value in them. That is what hoisting is using let.

  <img width="437" alt="image" src="https://github.com/user-attachments/assets/7d857f3f-d5b1-4460-979f-702e9969f204">

### Q> What is Temporal DeadZone?
Is the time since the let and const variables were hoisted and  till it is initialized some value. Time b/w that is called Temporal DeadZone.

**Note** → Even before a single line of code executed, we can see javascript allocated a memory for let variable in Script memory object but not assign any value (even not assign undefined )

### Q> How to avoid a temporal dead zone?
Push all the initialization and declaration on the top of the code.

### Q> Is let and const hoisted? 
Yes but they are facing temporal dead zone.

<img width="524" alt="image" src="https://github.com/user-attachments/assets/cbe8a437-17f5-43cb-b412-c50340014168">


## Errors while redeclare variable inside javascript

- Redeclare a let variable throws **SytanxError**. So you can not use the same name in the same scope  again.

  <img width="472" alt="image" src="https://github.com/user-attachments/assets/1122f023-7874-4165-b54b-0719fa887b39">

- In the case of const when you declare a variable with const it expects that you will initialize it in the same line otherwise it throws a **SyntaxError**.

  <img width="473" alt="image" src="https://github.com/user-attachments/assets/f378eb2b-e053-40bb-800a-73f72ebb091e">

- We cannot change the value of a const variable, it throws a **TypeError**.

  <img width="437" alt="image" src="https://github.com/user-attachments/assets/33925aec-c4c8-44b1-b3c3-47a57279591e">



##  Q> Explain this scenario.
<img width="472" alt="image" src="https://github.com/user-attachments/assets/a8c1c8cd-b6ec-4cf1-b0b2-873e3305df02">

in this case a is hoisted but it gives us a reference error because, at this point of time, a is in the temporal deadzone.

## Block in JavaScript

### Q> What is the block in JavaScript?
The block is used to combine multiple statements into one group.

<img width="474" alt="image" src="https://github.com/user-attachments/assets/e51246cb-a8b8-4d2b-a063-c7cb8fac5ae6">

### Q> What is block Scope?
It means all variables and functions we can access in this block.

***Note***: let and const variables are blocked scope, let's see an example.

  <img width="469" alt="image" src="https://github.com/user-attachments/assets/5b94b242-0fdc-4f0c-96f0-75377be88b3f">

* And in line, 40 let and const variables are no longer accessible. 
* We can not access this let and const variable outside of this block. Because it’s only in the block scope.
* Whereas we can access var even outside of the block because it is in the global scope.


<img width="470" alt="image" src="https://github.com/user-attachments/assets/ca7fa459-c933-4abe-8e50-460be3648bdc">


### Q> What is Shadowing in JavaScript?
<img width="497" alt="image" src="https://github.com/user-attachments/assets/35437455-89d3-4379-b8a6-53bf7b86a831">

<img width="497" alt="image" src="https://github.com/user-attachments/assets/c2c6f741-ec19-4e39-a2fa-1ad084476ec5">


### Q> What is illegal shadowing?
<img width="472" alt="image" src="https://github.com/user-attachments/assets/f8486f58-179a-4a3d-aaac-756fc6d38efe">

***Note***: var is a function scope

<img width="470" alt="image" src="https://github.com/user-attachments/assets/030184fa-f1d6-44d3-9999-a5566318166a">



***Note***:
- Shadowing let with let : possible
- let using var          : not possible
- var with let           : possible


## Q> What is Closures in js: 
Function along with its lexical scope bundle together to form a closure.

<img width="475" alt="image" src="https://github.com/user-attachments/assets/49df8dab-fda4-4f68-acf9-928626709336">
<br/>
<img width="475" alt="image" src="https://github.com/user-attachments/assets/02cb04a9-3de2-43c1-aea4-76df6e61d035">
<br/>
<img width="475" alt="image" src="https://github.com/user-attachments/assets/7b14319f-3cdd-4834-a912-b1678c413ba7">


## SetTimeout with Closures : 

<img width="470" alt="image" src="https://github.com/user-attachments/assets/70edef77-0bf9-4abc-b80f-69ee09e6c3ed">

**Q> What is the solution to fix this problem?**

Use let instead of var.  Because var has the glocal scope and let has blocked scope.So a new copy of i is created for every iteration

**Q> Can you find another solution where you can not use let, use var only:**

Use closures in every iteration so that it can create a new copy of i for itself.

<img width="470" alt="image" src="https://github.com/user-attachments/assets/c9fdbec0-b619-42a0-af6d-ed701714a9ee">

### Q>What are the advantages and disadvantages of closures?
**Advantages:**
- Module Design pattern
- Curring
- Function like once
- Memorize
- Maintaining state in the async world
- setTimeout functions
-Iterators
- Data hiding and encapsulation

**Disadvantages:**

- Over consumptions of memory
- Creating a function inside a function can lead to code duplication and slow down the application.
- Increase the Complexity

***Data hiding and encapsulation example***:
  counter variable can not be accessible from outside.

<img width="248" alt="image" src="https://github.com/user-attachments/assets/263205d6-d4a1-416a-ad4f-289e98139370">


## Q> Difference b/w function statement and function expression

<img width="450" alt="image" src="https://github.com/user-attachments/assets/5eddb178-5c7a-4d68-902b-9690bc09caa8">

## Q> What is Anonymous function?
A function without a name is called an anonymous function.
```function () {  }```

This type of function does not have an identity, so if you write an anonymous function like above it throws SyntaxError. Because based on ECMA script specification a function statement should always have a name.

the anonymous function used at a place where it is used as a value-like function expression.

## Named Function Expression: 

<img width="450" alt="image" src="https://github.com/user-attachments/assets/61e9caf0-55d3-49fc-b9a1-0cf07bce5778">
<br/>
<img width="450" alt="image" src="https://github.com/user-attachments/assets/b03fa0fb-ce15-4448-b53a-340ddc8c6e98">


## Q> What is the difference b/w parameters and arguments: 

<img width="356" alt="image" src="https://github.com/user-attachments/assets/b87cfb2c-c8ea-4a9e-95f1-092b29a2dc60">



## Q> What is the First Class function?
In JavaScript, a first-class function is a function that can be treated like any other value. This means that functions can be assigned to variables, passed as arguments to other functions, and returned from functions.

## Q> What is the First Class Citizen?
In JavaScript, functions are first-class citizens. This means that functions are treated like other data types like numbers and strings.

## Q> What is the Higher Order function?
A “higher-order function” is a function that accepts functions as parameters and returns a function.


## 🚀 Create a custom function like map and filter and assign it to Array.Prototype
**map**

```js
Array.prototype.myMap = function (cb) {
  let output = [];
  for (let i = 0; i < this.length; i++) {
    output.push(cb(this[i], i));
  }
  return output;
};

let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
let newArr = arr.myMap((item) => item * 2);
console.log(newArr);
```

**filter**

```js
Array.prototype.myFilter = function (cb) {
  let output = [];
  for (let i = 0; i < this.length; i++) {
    if (cb(this[i], i)) {
      output.push(this[i]);
    }
  }
  return output;
};

let arr2 = [1, 2, 3, 4, 5, 6, 7, 8, 9];
let newArr1 = arr.myFilter((item) => item % 2 == 0);
console.log(newArr1);
```

***Note:*** always use the function key to assign a function in the prototype otherwise it will not work.


## 🚀 Asynchronous JavaScript and Event loop
check this tutorial - [https://www.youtube.com/watch?v=8zKuNo4ay8E&list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&index=18](https://www.youtube.com/watch?v=8zKuNo4ay8E&list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&index=18)

  <img width="450" alt="image" src="https://github.com/user-attachments/assets/63689934-85f8-49df-a3be-b6fa854ac6e1">

- Anything that comes inside the call stack quickly executes, that how its works
- Browser gives access to the calltsack or the js Engine to use all the super power by using Global Object.
- Browser web apis are not part of JavaScript
- Global Object in the window object. Using this keyword, our call stack can access those web apis.


## 🚀 How setTimeout works?

<img width="450" alt="image" src="https://github.com/user-attachments/assets/f0f4989a-4daf-4d36-b882-dd486c76df68">

- When we pass a call-back function in setTimeout it registers the cb function into web APIs and attaches a timer.
- After the timer expires the callback function is put into the callback queue.
- Then the event loop checks if we have something in the callback queue and the call stack is empty or not  then the event loop takes the callback and pushes it into the call stack. And call stack quickly executes the callback function.

## 🚀 How the fetch function works?

<img width="450" alt="image" src="https://github.com/user-attachments/assets/5dc7b7f0-11d5-4da4-ab24-088f2a56d367">


- When we pass a call-back function in fetch it registers the cbF function.
- After the network call and in case of promises the callback function goes into the Micrtask queue.
- The event loop checks if the callstack is empty and then pushes the callback function into the callstack

***Note:***  The Microtask queue has higher priority than the callback queue.Functions under microtask queue are executed first and functions under callback queue are executed later.

## 🚀 What can come inside the microtask queue and callback queue?
| Microtask queue                                                                                                  | Callback queue/Task queue                                                              |
| -----------------------------------------------------------------------------------------------------------------| ------------------------------------------------- |
| All callback functions that come through promises will go inside the microtask queue and all mutation observers. | The callback function of setTimeout, DOM APIs.    |



## 🚀 Suppose three tasks are present in the microstack queue and three tasks are present in the callback queue then what will happen? 
Once all tasks inside the microtask queue are executed then the event loop gets the opportunity to execute those tasks inside the callback queue.

 
## 🚀 What is the Starvation of the callback queue?
We know the event loops give the higher priority to the microtask queue before any of the callback queue’s task. And suppose task inside microtask queue creates more tasks inside the microtask queue and goes on then the callback queue never gets a chance to execute for a long time. This is called starvation of the callback queue.

## 🚀 Trust issue with setTimeout : 
Here we try to block the main thread for 10 seconds.

<img width="550" alt="image" src="https://github.com/user-attachments/assets/9ebad9b1-334b-4960-a4e3-7a4065c2fa98">

## 🚀 What is Constructor Function in JavaScript?
A constructor is a special function that creates and initializes an object instance of a class. In JavaScript, a constructor gets called when an object is created using the new keyword. The purpose of a constructor is to create a new object and set values for any existing object.

Let's create Constructor function Counter and create two method incrementCounter and decrementCounter inside that function →

```js
function Counter(n) {
    this.count = n;
    this.increamentCounter = () => {
        this.count++;
    };

    this.decrementCounter = () => {
        this.count--;
    }
}
const obj = new Counter(5);
console.log(obj.count);
obj.increamentCounter();
obj.increamentCounter();
console.log(obj.count);
obj.decrementCounter();
console.log(obj.count);
```

## 🚀 Garbage collection in JavaScript:
Low-level languages like C, have manual memory management primitives such as malloc() and free(). In contrast, JavaScript automatically allocates memory when objects are created and frees it when they are not used anymore (garbage collection).

Low-level languages require the developer to manually determine at which point in the program the allocated memory is no longer needed and to release it.
Some high-level languages, such as JavaScript, utilize a form of automatic memory management known as garbage collection (GC). The purpose of a garbage collector is to monitor memory allocation and determine when a block of allocated memory is no longer needed.


Example →

<img width="450" alt="image" src="https://github.com/user-attachments/assets/5f3aafa2-f584-4afc-a6f6-888b361ffa7e">

- Here we define b but b is not being used. and when the func1 function is returned,  b is garbage collected and a is not.
- It's from a closure with a, and b just gone from the memory.


## 🚀 What is callback function in js?
A callback is a function that is passed as an argument to another function that executes the callback based on the result. They are functions that are executed only after a result is produced. Callbacks are an important part of asynchronous JavaScript.

## 🚀 What are the issues with the callback function?
- Call back hell
- Inversion of control.

**CallBack hell:** Callback Hell is essentially nested callbacks stacked below one another forming a pyramid structure. Every callback depends/waits for the previous callback, thereby making a pyramid structure that affects the readability and maintainability of the code. 

```js
function myFunc(res) {
    func1(res,function () {
        func2(res, function () {
		      // more nested functions
        })
    })
};
```

```js
 const animateAll = (animate) => {
        setTimeout(() => {
            animate(words[0]);
            setTimeout(() => {
                animate(words[1]);
                setTimeout(() => {
                    animate(words[2]);
                }, 1000)
            }, 1000)
        }, 1000)
    }
```

**Inversion of control:** We lose the control when we are using callback . So for example when we are passing a callback to another function(third party api call), we give the control from our code to the other code. And we don’t know if the other function will ever execute our callback function or not.

## 🚀 What are Promises in js?
- The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.
- This lets asynchronous methods return values like synchronous methods: instead of immediately returning the final value, the asynchronous method returns a promise to supply the value at some point in the future.
- JavaScript Promises to simplify managing multiple asynchronous operations, preventing callback hell, Inversion of control and unmanageable code.

  <img width="600" alt="image" src="https://github.com/user-attachments/assets/22ed9a4e-8782-49de-b4b6-5920b3094491">

**A Promise is in one of these states:**

- **pending:** initial state, neither fulfilled nor rejected.
- **fulfilled:** meaning that the operation was completed successfully.
- **rejected:** meaning that the operation failed.
  
Promise Objects are **Immutable**. (not editable).

Promise objects have two major properties. One is the **state**, Another one is the **result**


## 🚀 What is Promise Chaining?
Promise Chaining is a simple concept by which we may initialize another promise inside our .then() method and accordingly, we may execute our results. The function inside then captures the value returned by the previous promise.

```js
const promise = new Promise((resolve, reject) => {
    resolve("Hello js");
});
promise
.then((res1) => {
    console.log("1st then", res1);
    return new Promise((resolve, reject) =>{
        resolve("We are awesome")
    })
}).then((res2) => {
    console.log("2nd then", res2);
}).catch((err) => console.error(err))
```
