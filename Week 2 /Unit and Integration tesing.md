---
title: Unit and Integration testing
tags: Unit, Integration ,testing
description: A presntation for two types of testing
---

# What is testing?
Testing is a big part of development, to ensure your application does what it is supposed to do.

---
Here we will talk about two types of testing:
-Unit testing

-Integration testing

---

## Unit testing

---

-Unit is a section of your application usually one function.
- A unit test is meant to test a function or certain precdure.
- It is usually automated and done by the developer.

---

## Advantages
- Isolate each part of the program to ensure its correct.
- Finds problems early in the development cycle


---

# Disadvantages
- Testing will not catch every error in the program.
- it will not catch integration errors or broader system-level errors.
- setting up realistic tests that behave like a part of the real system is challenging.

---


# Applications 
- TDD (Test Driven Development).
- Extreme programming : a development paradigm "test everything that can possibly break"


---

## Integration testing

---

- A Integration test tests how multiple parts of the program work together.
- It relies heavily on manual human testing.

---

## There are two types of Integration testing.
- Big Bang testing:
Wait for every componet to be deveolped then finish test everything together.
- Incremental testing:
Test each individual componet and integrate either a "Driver" or a "Stub" 
 ( more on those in examples)

---


# Examples!

![](https://i.imgur.com/od2KnXs.png)



---


### Conclusion

---

* Unit testing is used along side integration testing , even multiple unit tests does not make up for integration testing.
* Intergation testing is the broader test and it unit testing will be used alongside.

---



---

### Thank you! 