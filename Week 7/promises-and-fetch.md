# Promises and Fetch
By @logicx1 and @ivankhuri

---


# Promises

---

### In short
Promises are pieces of code used to handle asynchronous operations in JavaScript. This lets asynchronous methods return values by returning a promise that will supply the value at some point when it is available.

---

## States of a promise
### Pending
The promise is yet to be fulfilled or rejected.
### Fulfilled
The operation completed succefully.
### Rejected
The operation failed.

---

## Creating a promise:
We create a promise using the "new" keyword as follows : 
```
let myFirstPromise = new Promise(
function(resolve, reject){
// Do things ..
});
```

---

## Handling promises:
After the promise we need to handle the two possible cases:

---

### Promise fullfiled:
We follow it with a `.then(function(result){..}) `
It takes a callback as parameter,and calls it the result of the fullfilled promise.
### Promise rejected:
We need a `.catch(function(error){..})` 
It takes a callback to deal with the error.

---

![](https://i.imgur.com/Bq2VB3U.png)

---

## Basic example
```
let myFirstPromise = new Promise((resolve, reject) => {
  setTimeout(function() {
    resolve("Success!");
  }, 250);
});

myFirstPromise
.then(successMessage => {
  console.log("Yay! " + successMessage);
})
.catch(error =>{
  console.log(error);
})
;
```

---

## Fetch

The Fetch API provides a JavaScript interface for accessing and manipulating parts of the HTTP pipeline, such as requests and responses. It also provides a global fetch() method that provides an easy, logical way to fetch resources asynchronously across the network.

---

## Fetch disadvantages

The main disadvantage of fetch is that it _only_ rejects requests in the case of a network error. That means if the request returns 404, it will appear to be successful.

---

## Advantages of promises

---

* Better readabilitiy : 
  Allows us to write asynchronous code the same way we write synchronous code
  Similar to synchronous programming; output of one function is the input of the next one
  

---

```
  Example:
  get("/countries")
  .then(populateContDropdown)
  .then(countries =>  get(countries/${countries[0].id}/cities))
  .then(populateCitiesDropdown)
  .then(cities => get('cities/${cities[0].id}/universities'))
  .
  .
```
  

---


* Avoid callback hell
* Promises let asynchronous methods return values by returning a promise.
* Reduced coupling:
  Unlike callbacks,we don't have to prepare the callbacks, and chain callbacks ahead of time making our code very tightly coupled.

---

* Better error handling
You can put catch handler anywhere in the chain to catch the specific exceptions.
```
get("/countries")
  .then(JSON.parse)
  .catch(e => console.log("Could not parse string"))
  .then(...)
  .catch(e => console.log("Error occured"))
```





---

## Disadvantages of promises

* Increases CPU usage
* Defeats the purpose of asynchronous non-blocking code


---

## Soruces : 

[The Mozilla documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

[Advantages of promises - medium.com](https://medium.com/@mohsanriaz224/advantages-of-using-javascript-promises-dd45f72d1e49)


---

# Thank you!


---
