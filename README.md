# Core Concept of JavaScript


## Execution Context:
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

