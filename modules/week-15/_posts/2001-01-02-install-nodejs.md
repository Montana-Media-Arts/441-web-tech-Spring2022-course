---
title: Install node.js
module: 14
jotted: true
---

# Install node.js

There is an option to try node.js without installing it. It's located here.

<a href="https://www.tutorialspoint.com/execute_nodejs_online.php" target="_new">Online node.js</a>

### Local Environment Setup

If you are still willing to set up your environment for Node.js, you need the following two softwares available on your computer
- (a) Text Editor 
- (b) The Node.js binary installables.

**Text Editor**

This will be used to type your program. Examples of few editors include Windows Notepad, OS Edit command, Brief, Epsilon, EMACS, and vim or vi.

Name and version of text editor can vary on different operating systems. For example, **VS Code** or **Atom** will work just fine.

The files you create with your editor are called source files and contain program source code. The source files for Node.js programs are typically named with the extension ".js".

**The Node.js Runtime**

The source code written in source file is simply javascript. The Node.js interpreter will be used to interpret and execute your javascript code.

Node.js distribution comes as a binary installable for SunOS , Linux, Mac OS X, and Windows operating systems with the 32-bit (386) and 64-bit (amd64) x86 processor architectures.

The following section guides you on how to install Node.js binary distribution on various OS.

**Download Node.js archive**

Download latest version of Node.js installable archive file from Node.js <a href="https://nodejs.org/en/download/current/" target="_new">Downloads</a>. 

**Verify installation: Executing a File**

Create a js file named `main.js` on your machine (Windows or Linux) having the following code.

```js
/* Hello, World! program in node.js */
console.log("Hello, World!")
```

Now execute `main.js` file using Node.js interpreter to see the result, make sure you navigate to the directory where you saved your file. Then, type the following in your console.  

```js
node main.js
```
If everything is fine with your installation, this should produce the following result −

`Hello, World!`
