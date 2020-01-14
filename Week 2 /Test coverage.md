# <center>**Test Coverage**</center>

**<center>Team LAR</center>**

---

***What is test coverage?***

Test coverage is an important indicator in software testing in terms of quality and effectiveness. 

Test coverage is defined as a technique which determines whether our test cases are actually covering the application code and how much code is exercised when we run those test cases.

If there are 10 requirements and 100 tests created and if 90 tests are executed then test coverage is 90%. Now, based on this metric, testers can create additional test cases for remaining tests. Below are some more advantages of test coverage.

---
**<center>Statement Coverage</center>**

All the statements in the source code are tested at least once. In complex code, a single path is not sufficient to cover all the statements. In that case, you need to write multiple test cases to cover all the statements.

![](https://www.simform.com/wp-content/uploads/2018/03/statement-coverage.png)

*Advantages:*
* It can be applied directly to object code and does not require processing source code.
* It verifies what the written code is expected to do and not to do

*Disadvantages:*
* It covers only true conditions of every statement.
* Does not report when loop reaches to the terminations.
* Statement coverage is completely insensitive to the logical operators (|| and &&).

---
**<center>Decision/Branch coverage</center>**

Checks every possible path or branch in the code is covered.
![](https://www.simform.com/wp-content/uploads/2018/03/branch-coverage.png)
*Advantages:*
* It covers both the true and false conditions unlikely the statement coverage.
* It validates if all branches are tested.

*Disadvantages:*
* It ignores branches within Boolean expressions which occur due to short-circuit operators.

---
**<center>Path Coverage</center>**

Path testing is a structural testing method that involves using the source code of a program in order to find every possible executable path.

![](https://www.simform.com/wp-content/uploads/2018/03/path-coverage.png)

*Advantages:*

* It helps to reduce redundant tests.
* Path coverage provides high test coverage because it covers all statements and branches in the code.

*Disadvantages:*

* Testing each path is challenging as well as time-consuming because a number of paths are exponential to the number of branches. For example, a function containing 10 if-statements has 1024 paths to test.
* Sometimes many paths are impossible to exercise due to relationships of data.

---
**<center>Condition Coverage</center>**

Condition coverage checks if both the outcomes(“true” or false”) of every condition have been exercised. The outcome of the decision point is only relevant for checking the conditions. It requires two test cases per condition for two outcomes.

*Advantages:*

* Condition coverage measures the conditions independently of each other.
* It has better sensitivity to the control flow.

*Disadvantages:*

* Similar to the branch/decision coverage.

---
**<center>Boundary Value Coverage</center>**

This coverage metric is very useful for those applications in which error occurred due to input numbers. And these errors occurred at boundary values. In boundary value coverage, test cases are selected at the endpoints of the equivalence classes. For this test coverage example, below are boundary values for an application which requires 3-digit number as an input.

*Advantages:*

* It is quite easy to test a small set of data in place of testing a whole lot of data sets.
* It is easy to use because of it’s easy to automate nature and uniformity of identified tests.

*Disadvantages:*

* It can not test dependencies between two inputs.
* It can not cover code which contains boolean functions.

---

***Why is test coverage useful?***

Test Coverage can help us assess the code we are writing, in order for us to do so, we sometimes use Test Coverage Metrics.Test coverage metrics can be divided into three parts: code-level metrics, feature testing metrics and application level metrics.

**Code level metrics** - It also called as executed tests and it is a percentage of passed/executed tests out of the total number of tests.

**Feature testing metrics** - Requirements coverage is used to determine how well the test cases cover the software requirements.

**Application level metrics** - measure of the total known defects divided by the size of the software entity being measured.



---


***Use Jest to calculate your code coverage for the TDD workshop***
Step 1) The total lines of code in the piece of software you are testing

Step 2) The number of lines of code all test cases currently execute 

Now, you need to find (X divided by Y) multiplied by 100. The result of this calculation is your code coverage %.

![](https://www.guru99.com/images/jsp/030116_0814_LearnStatem1.png)

The TDD workshop example:
Lines of code: 14.
Test covered lines: 14.
(14/14)*100 = 100%

We run: npm run test:coverage to start the test.
(after adding "test:coverage": "jest --coverage")

----------|----------|----------|----------|----------|-------------------|
File      |  % Stmts | % Branch |  % Funcs |  % Lines | Uncovered Line #s |
----------|----------|----------|----------|----------|-------------------|
All files |      100 |      100 |      100 |      100 |                   |
 index.js |      100 |      100 |      100 |      100 |                   |
----------|----------|----------|----------|----------|-------------------|

---
***How would you use code-coverage to improve your testing?***

As the product development progresses, new features, as well as fixes are added. Test code may require changes in order to keep it updated with the software changes made during developmentso it's important that the testing standards which were set during the start of the project are maintained. Code coverage can be used to make sure that your tests are meeting those standards and the best quality code goes into the production phase and it's <u>measured by calculating the percentage of code that is covered during testing.</u>
The higher percentage of code coverage; the lower are the chances of having undetected bugs. 

---
***References***
https://www.simform.com/test-coverage/
https://www.guru99.com/test-coverage-in-software-testing.html
https://www.lambdatest.com/blog/code-coverage-vs-test-coverage/