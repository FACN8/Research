## Deploying & Cloud Platforms
![image alt](https://cdn.lynda.com/course/612191/612191-636670874505100724-16x9.jpg)

---

### Cloud Computing
#### General Definition:
Cloud computing is a type of computing that relies on shared computing resources rather than having local servers or personal devices to handle applications.

---

## What is PaaS?
<p style="font-size:30px">
PaaS stands for "Platform as a Service" or "Application Platform as a Service".<br>
PaaS, which is a category of cloud computing services provides a platform which allows to develop, run, and manage applications without the complexity of building and maintaining the infrastructure typically associated with developing and launching an app.
</p>

![image alt](https://lh6.googleusercontent.com/bBMwzvYTOEH2i8Buf1FnOfscv5rw8bhtTuLoNzXQHGlK9tySXrAa5RbwCGi5FLY5mQIl7d1_6au9xrPKhaLSsGELWlDpYMjYAKU-Gz6BB40ebC4rK-pDtfBVm00ifNs_C2miTGvx)


---

![image alt](https://www.milesweb.com/images/paas/paas-architecture.png)

---

![image alt](https://miro.medium.com/max/1313/1*0z9Pqwn7ujypQ396wleJ1Q.png)

---

## So why is it useful/important? 
<ul style="font-size:34px">
<li><strong style="color:red">Time and Money:</strong> building and maintaining infrastructure which includes servers and databases.</li>

<li><strong style="color:red">Fast Development & Delivery Of Apps:</strong> gain a competitive edge or the need to get products to market quickly.</li>

<li><strong style="color:red">Quick To Test:</strong> test the use of new languages, operating systems, databases, and other developmental technologies quickly.</li>

<li><strong style="color:red">Supports Remote Work:</strong> Good for large companies that have different teams across the globe.</li>

</ul>

---

#### A good platform to use for your code is - HEROKU:

![image alt](https://miro.medium.com/max/3600/1*fIjRtO5P8zc3pjs0E5hYkw.png =500x200)

 If you access [This Website](https://appdividend.com/2018/04/14/how-to-deploy-nodejs-app-to-heroku/) it will provide you with a demo about how to go on about installing a simple service.
 ### <h3 style="color:red">Caution: Uses Express!</h3>

---

## Environment variables:

Environment variables are values that impact the processes and behavior of running computer systems and OS environments. <br>
Environment variables are the best way of storing <strong><span style="color:red">sensitive data</span></strong>  like API Keys, Login Credentials and Database Passwords.

---


### Why might some variables in your code need to change for different environments?

According to the environment, our code might need run differently, so wherever our app/code needs configuration, we could use environment variables. 


---

### Why is it a bad idea to include those variables in a public repository?


When we are using these variables in a public repository we are publishing in the open so that anyone can see it. Thus, attackers might gain access to our sensitive data, including API keys.

---

### What modules might you use to help manage environment variables?

<b>Dotenv</b> is a zero-dependency module that loads environment variables from a `.env` file into [`process.env`]

<!-- The Environment Modules package is a tool that simplify shell initialization and lets users easily modify their environment during the session with modulefiles.

It has the responsibility of gathering environment variables. This makes it easy to see them all at once and map them to readable names. -->

![](https://i.imgur.com/6ISv4hk.png)


---

<h4>
References:
</h4>

* https://medium.com/the-node-js-collection/making-your-node-js-work-everywhere-with-environment-variables-2da8cdf6e786

---

# Thank You !!

![image alt](https://i.pinimg.com/originals/6e/8d/02/6e8d02b5b25452265380cc69f062f539.png =x500)