# Asynchronous JavaScript

---

**First class functions**

First class functions are functions that are treated like any other object and can be passed as arguments. In JavaScript, functions are first class functions.
<br>
```
const foo = function() {
    console.log("foobar");
}
// Invoke it using the variable
foo();
```

---

**Higher order functions**

**Higher order functions** are functions that take other functions as arguments and/or return functions as their results.
<br>

```
[1, 2, 3, 4].map(function(n) {
    return n * 2
});

//[ 2, 4, 6, 8 ]

```

---

**Call Stack**
**The call stack** is a data structure that stores information about the run-time tasks that the program has to run.

---

![](https://i.imgur.com/5xAZgRy.jpg)

---

**Asynchronous functions**

**Async functions** operate in a separate order from the call stack, and are invoked using the event loop.

<br>

```
function doAfter2Seconds() {
    setTimeout(function() {
        console.log('Ok boomer');
    }, 2000);
}
doAfter2Seconds();

// The function is now asynchronous and the code
// will run after 2 seconds & the call stack is empty.

```

---

**Blocking code**

Blocking code is code that prevents the program from executing further code, because it is synchronous and is running resource heavy tasks or API calls that take time to complete.
<br>
```
const fs = require('fs');
const data = fs.readFileSync('/file.md');

//Blocks the callstack until the file is read
```

---

**Callback functions**
**A callback function** is a function that is given as an argument to another function and is expected to execute at any given time during the higher-order function's execution.

---

```
function higherOrderFunction(callback) {
    callback(10);
}

higherOrderFunction(function callbackFunction(number) {
    console.log(number); //OUTPUTS 10
});

//In this example, the function higherOrderFunction
//takes an argument callback function and invokes it.

```

---

**CAST**
<br>
Fatmeh -------- VISUAL EFFECTS DIRECTOR
<br>
Ivan -------- CLASS CLOWN
