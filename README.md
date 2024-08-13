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

<img width="473" alt="image" src="https://github.com/user-attachments/assets/ce76e352-9b6c-4b1a-a5e5-7d8eda32f77b">

