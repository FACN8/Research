# Streams and Buffers
Today we will learn about:
* What streams and buffers are in Node
* Why do we need them
* How are they used together


---

### Gernally in Computer Science: 
 Stream is a sequence of data elements made available over time.

Buffer is a region of a physical memory storage used to temporarily store data.

---

## Why do we need streams

To handle and manipulate streaming data like a video, a large file, etc.
Streams can be used to both read and write data.


## Why do we need buffers ?
To hold the data for the stream to consume.
A buffer is a temporary memory that a **stream** uses to hold data.

---


##  Streams in Node

Node.js streams extend the [EventEmitter](https://nodejs.org/api/events.html#events_class_eventemitter) class. We can listen to events like data and end in streams.

```
stream.on('data',callback);

stream.on('end',callback);
```



---

## Flowing and Non-Flowing Streams
### There are two types of readable streams:

---


# Flowing stream 
A stream that keeps on passing the data that can be directly listened to by using the data event on the stream.

---


# Non-flowing stream 

A stream that does not push data automatically. Instead, the stream stores the data in the buffer and we need to explicitly call the read() method of the stream to read it.

The following is a simple example of a non-flowing stream:

---

```
const fs = require('fs');

var readStream= fs.createReadStream('./data.txt');

setTimeout(() => {
  const data = readStream.read(10);
  console.log(data);
}, 10);
```

---



## Type of streams in Node 

### Readable streams

 To create a stream of data for reading (say, reading a large file in chunks).
 `fs.createReadStream()`
 
 An example for setting up a readable **flowing stream.**
 

---

```
const fs = require("fs");
const filePath = process.argv[2];

try {
  let stream = fs.createReadStream(filePath);

  stream.on("data", chunk => {
    process.stdout.write(chunk);
  });
```

```
  stream.on("error", () => {
    console.log(
      "error while reading the file"
    );
  });
} catch (x) {
  console.log("An error has ocurred");
}
```


---


### Writable streams 
To create a stream of data for writing (say, writing a large amount of data to a file).
```
fs.createWriteStream()
```

---

### Duplex streams

To create a stream that is both readable and writable at the same time. We can read and write to a duplex stream (say, a socket connection between a client and a server).
for example, [net.Socket](https://nodejs.org/api/net.html#net_class_net_socket).

---

### Transform streams

To create a stream that is readable and writable, but the data can be modified while reading and writing to the stream (say, compressing data by the client and server before while requesting).
for example, [zlib.createDeflate()](https://nodejs.org/api/zlib.html#zlib_zlib_createdeflate_options)


--- 



---


## Buffers in Node

### Buffer size 
Buffer has a limited size, you can read about it [here](https://nodejs.org/api/stream.html#stream_buffering)

Normally if we try to push some data into the stream, the data is pushed into the stream buffer. The pushed data sits in the buffer until the data is consumed.

**If the buffer is full** the stream does not accept more data and returns a false value.


---

## Buffer Management by the Read Stream

* This can be done using read method on the read stream , it takes the number of byes to read as an argument.

### An example to explain this :

Here we read each 10 bytes from the buffer then log the data.

---

```
const fs = require('fs');

var readStream=fs.createReadStream('./data.txt');

setTimeout(() => {
  const data = readStream.read(10);
  console.log(data);

  const data2 = readStream.read(10);
  console.log(data2);
}, 10);
```


---

# Conclusion 

* You can create streams using the methods from the 'fs' module  for example:
 ```
const fs = require('fs');
 var readStream = fs.createReadStream('file_path');
```
* The data in streams are instance of the [Buffer Object](https://nodejs.org/api/buffer.html#buffer_buffer)

* Console.log(chunk) prints out a text representation of the buffer (array of bytes)
* proccess.stdout.write(chunk) prints the chunk in readable format.

* process.stdout is also a stream for standard output.





---



# Thank you 