# Express MidelleWares

---

## What are express middlewares?

### Express middleware are functions that execute during the lifecycle of a request to the Express server. Each middleware has access to the HTTP `request` and `response` for each route it’s attached to.

---

![Express](https://i.imgur.com/QhJ3ttc.png)

---


## what functionality express middlewares provide?

### 1) Execute any code. 

### 2) Make changes to the request and the response objects. 

### 3) End the request-response cycle. 

### 4) Call the next middleware in the stack. 

---

### If the current middleware function does not end the request-response cycle, it must call `next()` to pass control to the next middleware function. Otherwise, the request will be left hanging.

---

## Types of middleware express functions:

### 1) Application-level middleware

      Bind application-level middleware to an instance of 
      the app object by using the app.use() 
      and app.METHOD() functions   


---

### 2) Router-level middleware

![](https://i.imgur.com/HH2TxYY.png)

---

### 3) Error-handling middleware

### Express has a built-in default error handler that is inserted at the end of the middleware pipeline that handles any unhandled errors that may have occurred. For Example:

---

```express
app.get('/', (req, res) => {
    res.sendFile(path.join
    (__dirname, '..', 'public', 'index.html'));
});

app.use((err, req, res, next) => {
   console.log('my error is:', err);  
   res.status(500).sendFile(path.join
   (__dirname, '..', 'public', '500.html'))
});
```

---

### 4) Built-in middleware

![](https://i.imgur.com/Xf8OTuX.png)

---

### 5) Third-party middleware

      Use third-party middleware to add functionality to Express apps.


![](https://i.imgur.com/tnUvMuS.png)

---

## Armoring the API with Helmet

- Configures the Content Security Policy;
- Removes the header X-Powered-By that informs the name and the version of a server;
- Configures rules for HTTP Public Key Pinning;
- Configures rules for HTTP Strict Transport Security;
- Treats the header X-Download-Options for Internet Explorer 8+;

---

- Disables the client-side caching;
- Prevents sniffing attacks on the client Mime Type;
- Prevents ClickJacking attacks;
- Protects against XSS (Cross-Site Scripting) attacks.

---

![](https://i.imgur.com/gTNmktx.png)

---

# cors

As we are developing an API that will serve data for any kind of client-side applications,macking endpoints become public. Meaning that some clients can make requests on our API.

---

```express
app.use(cors({
    origin: ["http://localhost:3001"],
    methods: ["GET", "POST"],
    allowedHeaders: ["Content-Type", "Authorization"]
}));
```

Now we have an API that will only allow client apps from the address: http://localhost:3001/. This client application can only request via GET or POST methods and use the headers: Content-Type and Authorization.

---

# morgan

## Generating logs

set up our application to report and generate logs files about the user’s requests.

---

![](https://i.imgur.com/GHYkSud.png)

---

# compression

#### Compacting requests using GZIP middleware

make requests lighter and load faster

---

<img src="https://i.imgur.com/ZfRru7J.png" alt="Smiley face" height="650" width="1000">

---

# example for all the above will be explained with live coding

---

# Thanks for you attention