# Packaging
What is packaging?
Packaging is organizing a related collection of "modules" and code
that usually handles one issue.

A set of multiple packages is called a "Library".

---

## Dependencies
* A dependency is additional code that your program can use.
* Dependencies can be libraries, tools, or modules.
* You can write your own, or use third party dependencies.
* Dependencies save a lot of time and prevents repeating work.

---

### Why not write your own?
#### Avoid unecesssary work
* Dependencies tend to be large, and even if you know how to create one, it takes a long time.
#### Don't try to re-invent the wheel
* Dependencies such as popular libraries are well made and maintained therefore using them will merit a smoother program.

---


## Issues with managing dependencies


---


#### Managing dependencies is not easy, and especially if you are relying on third party dependencies.
<br>
Third party libraries often depend on other libraries. This may mean library A depends on C v1.2, and library B depends on C v1.1, meaning A and B are incompatible.

---

#### Installing & Updating
* Traditionally downloading, installing, and updating dependencies was a tedious manual job.
* Dependency Managers aka Package Managers solve this by automating the downloading and installation of dependency packages.

---

### Example for an application with its dependencies
Node.js requires the following dependencies to work: 


| <b>Libraries</b> | <b>Tools</b> |
| --------- | ----- |
| V8        | npm   |
| libuv     | gyp   |
| llhttp    | gtest |
| c-ares    |       |
| OpenSSL   |       |
| zlib      |       |

** Note: Dependencies can be written in different languages, like the V8 engine is made with C++ by google.


---


## NPM
<!-- How does it help with dependencies
 -->
NPM (Node Package Manager) is software that automates installing, updating, configuring, and removing modules (dependencies), and is one example of a package manager.

---

To use npm, first navigate to your package's directory in terminal, and run the following command, and we use '-y' to get the default values in our package.json:
> `npm init -y`

---

You should now have '`package.json`' in that directory. In order to install a module (dependency) run the following command:
> `npm install <module-name>`

This installs packages locally and will be stored in ./node_modules.

---

 <!-- What is package.json, and what does npm init do? -->
### What is package.json?
This file helps npm identify the project and manage its dependencies. It contains other metadata & properties, but we won't get too into detail.

---

### Global Dependencies

The -g flag installs the module globally to your machine, rather than into the node_modules folder of that specific project.

> `npm install -g <package-name>`

It is not recommended to install packages globally unless you really have to, since it is all stored in the same place and can get messy.

---

### Dev Dependencies
Dev Dependencies are modules which are **only** required during development.

> npm i --save-dev <package>

for short:
> npm i -d <package>

--save-dev saves it under devDependency in package.json.

---

Dev dependencies, unlike regular dependencies, are only needed in the development stage while the latter is also required at runtime.
<br>
If you **only** need a module for development, it should be strictly added as a ***dev dependency*** to avoid installing unneccesary packages for users.

---

### To use a module in your code:

> const module-name = require('module-name');
> 
> module-name.doSomething();

---

### To use a module in the terminal:

> npm run <command>

this will run the command from your "scripts" in package.json

---

### Node modules

NPM installs packages in a folder called node_modules in your project's root directory. It is not recommended to share this file with others working on this project, like on Github for example.

---

This is where .gitignore comes in to place.
.gitignore is a file that tells Git what to ignore and not upload to the repository. To ignore a file, we simply add the file name in .gitignore, separated by a coma:

> node_modules,
>
> another_file,
>
> and_another_file