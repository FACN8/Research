---
title: Research on Engineering
tags: Research, Talk,presentation
description: Research on Engineering with presentation.
---

# join us 

slide: https://hackmd.io/@FACN8/Engineering

---

# Engineering


---

![](https://i.imgur.com/haqhAjS.jpg)


---

#### Modularising a codebase leads to very direct benefits such as:

<style>
li{
font-size:34px;
}
p{
font-size:34px;
}
</style>

- Ease of code sharing within a team: Many developers can work on disparate features without leading to code conflicts within a version control system

- Ease of code sharing between the front-end and back-end components of your stack: An isolated module which does one thing only is primed to be used on more than one layers of your technology stack

- Simplified code maintainability: Your understanding of where changes need to be made increases

---

## what is require and module.exports?

---

### Create Your Own Modules

You can create your own modules, and easily include them in your applications.
Use the <b>exports</b> keyword to make properties and methods available outside the module file.

The following example creates a module that returns a date and time object:
```javascript
exports.myDateTime = function () {
  return Date();
  };
```

---

### Include Modules

To include a module, use the <b>require()</b> function with the name of the module:

```javascript
var http = require('http');
var currentTime = require('./myfirstmodule');

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.write("The date and time are currently: " 
  + currentTime.myDateTime());
  res.end();
}).listen(8080);
```

Why can't you use them in the browser? well...
<b> require(), module.exports and exports</b> are APIs of a module system that is specific to Node.js. Browsers do not implement this module system.

---

## How might you modularise client-side code?

- <b>Split code into multiple files</b> (as needed) and wrap those files with <code> (function(){/* your code */})(); </code>to create private scope. If you're using other libraries or other global objects.
- <b>Leverage script loading when necessary</b> (and not on initial page load) so that you have the flexibility to load modules on demand, in proper dependency order.
- <b>Use Object Orientation.</b>
- <b>Use "namespaces".</b>

---

## Asyncronous functions:

* JavaScript is a synchronous programming language. But thanks to promoises and callback functions we can make it function like Asynchronous programming language.

---


## What is an asyncronous function?

- The function operates asynchronously via event loop.
- It uses an implicit Promise to return the result.
- The syntax and structure of the code is similar to writing synchronous functions.
- Asynchronous code executes without having any dependency and no order.


---

## What is an asyncronous programming?

* Asynchronous programming is great for faster execution of programs but its difficult to program. It is a design pattern which ensures the non-blocking code execution.

* Callbacks enable a balanced, non-blocking flow of asynchronous control across modules and applications.

* A “callback” is passed as an argument to be called once the rest of that code has been run. This allows different functions to asynchronously hand control back and forth across an application.

---

### Why should you use asyncronous forms of functions wherever possible in Node?

* Node.js relies on asynchronous code to stay fast, so having a dependable callback pattern is crucial. Without one, developers would be stuck maintaining different signatures and styles between each and every module.

* The error-first pattern was introduced into Node core to solve this very problem, and has since spread to become today’s standard. While every use-case has different requirements and responses, the error-first pattern can accommodate them all.

---

## What are error-first callbacks?

Error-first callbacks:
Most asynchronous methods exposed by the Node.js core API follow an idiomatic pattern referred to as an error-first callback. With this pattern, a callback function is passed to the method as an argument. When the operation either completes or an error is raised, the callback function is called with the Error object (if any) passed as the first argument. If no error was raised, the first argument will be passed as null.

---

## What are error-first callbacks?

There’s really only two rules for defining an error-first callback:

* The first argument of the callback is reserved for an error object. If an error occurred, it will be returned by the first err argument.
* The second argument of the callback is reserved for any successful response data. If no error occurred, err will be set to null and any successful data will be returned in the second argument.

---

## Example

```javascript
fs.readFile('/foo.txt', function(err, data) {
  // TODO: Error Handling Still Needed!
  console.log(data);
});
function errorFirstCallback(err, data) {
  if (err) {
    console.error('There was an error', err);
    return;
  }
  console.log(data);
}
fs.readFile('/some/file/that/does-not-exist', errorFirstCallback);
fs.readFile('/some/file/that/does-exist', errorFirstCallback);
const fs = require('fs');
```

---

fs.readFile() takes in a file path to read from, and calls your callback once it has finished. If all goes well, the file contents are returned in the data argument. But if somethings goes wrong (the file doesn’t exist, permission is denied, etc) the first err argument will be populated with an error object containing information about the problem.

---

## why is it important to follow that pattern in your code?

* When a function passes its errors to a callback it no longer has to make assumptions on how that error should be handled. readFile() itself has no idea how severe a file read error is to your specific application. Instead of having to decide itself, readFile() propagates it back for you to handle.

* When you’re consistent with this pattern, errors can be propagated up as as many times as you’d like. Each callback can choose to ignore, handle, or propagate the error based on the information and context that exist at that level.

---

```javascript
if(err) {
  // Handle "Not Found" by responding with a custom error page
  if(err.fileNotFound) {
    return this.sendErrorMessage('File Does not Exist');
  }
  // Ignore "No Permission" errors, this controller knows that we don't care
  // Propagate all other errors (Express will catch them)
  if(!err.noPermission) {
    return next(err);
  }
}
```
<p style="font-size: 26px">
Its up to you, the callback creator, to properly handle this error. You can throw if you want your entire application to shutdown. Or if you’re in the middle of some asynchronous flow you can propagate that error out to the next callback. The choice depends on both the situation and the desired behavior.</p>


---

### Input/output (the fs and path modules):
What kind of tasks does the fs module enable you to perform that you wouldn't be able to in the browser? What are some of the issues of working with paths when accessing a file system? How does the path module help, and why should you use it instead of manually writing file paths as strings?

---

### What tasks can be done by FS Module:

tasks that need access to the file system, for example:

- Read files
-   Create files - fs.writeFile(), fs.appendFile(),fs.open()
- Update files 
- Delete files
- Rename files

---

### why fs is being used in Node.js and not in browser?

---

### why fs is being used in Node.js and not in browser?
    more safe, and more easy

---

```javascript=
var http = require('http');
var fs = require('fs');
http.createServer(function (req, res) {
  fs.readFile('demofile1.html', function(err, data) {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write(data);
    res.end();
  });
}).listen(8080);

```

---

### What are some of the issues of working with paths when accessing a file system?

---

### What are some of the issues of working with paths when accessing a file system?

not to make a human mistake, help avoid bugs and errors.
 Windows does paths with backslashes where Unix does paths with forward slashes. node.js provides path.join() to always use the correct slash

---

#### example of path functions which avoid human mistakes:

```javascript=

path.join('/foo', 'bar', 'baz/asdf', 'quux', '..');
// Returns: '/foo/bar/baz/asdf'

path.normalize('C:\\temp\\\\foo\\bar\\..\\');
// Returns: 'C:\\temp\\foo\\'

path.relative('C:\\orandea\\test\\aaa', 'C:\\orandea\\impl\\bbb');
// Returns: '..\\..\\impl\\bbb'

```

path.join('a/','b'), path.join('a/','/b'), path.join('a','b') and path.join('a','/b') will all give a/b.


---

## Working with URLs 
### (the url and querystring modules)

![](https://i.imgur.com/osqsMfd.jpg)

---

### URL objects

The built-in URL class provides a convenient interface for creating and parsing URLs.

There are no networking methods that require exactly an URL object, strings are good enough. So technically we don’t have to use URL. But sometimes it can be really helpful.

---

## URL structure
URL address has a determined structure which includes:

- method of access to the resource that is also named the network protocol.
- access authorization.
- hosts – DNS address that is inscribed as IP address.
- port – one more obligatory detail included in combination with IP address.
- track – determines the information about the method of gaining access.
- parameter – the internal information of resource about the file.

---

![](https://i.imgur.com/cdEE9L7.jpg)

---

## URL Encoding 

URL Encoding converts reserved, unsafe, and non-ASCII characters in URLs to a format that is universally accepted and understood by all web browsers and servers. It first converts the character to one or more bytes. Then each byte is represented by two hexadecimal digits preceded by a percent sign (%) - (e.g. %xy). The percent sign is used as an escape character.

---

## using URL Encoding 

| Before | https://hackmd.io/@FACN8/Engineering |
| -------- | -------- |
| After | https%3A%2F%2Fhackmd.io%2F%40FACN8%2FEngineering   |

---

# Thank you! :sheep: 

(https://codeforgeek.com/asynchronous-programming-in-node-js/)
(https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
(http://fredkschott.com/post/2014/03/understanding-error-first-callbacks-in-node-js/)
(https://nodejs.org/api/errors.html)