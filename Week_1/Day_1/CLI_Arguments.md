# Command Line Arguments in Node.js

Command line arguments are strings of text used to pass additional information to a program when an application is run through the command line interface (CLI) of an operating system. Command line arguments typically include information used to set configuration or property values for an application.

In most cases the arguments are passed after the program name in your prompt. An example of the syntax of command line arguments looks like this:

` $ [runtime] [script_name] [argument-1 argument-2 argument-3 ... argument-n]
`

Here, runtime can be anything that executes a program/script (e.g. sh, java, node, etc.) The arguments are usually separated by a space - however there are some runtimes that use commas to distinguish between multiple command line arguments. 

The simplest way of retrieving arguments in Node.js is via the `` process.argv `` array. This is a global object that you can use without importing any additional libraries to use it. You simply need to pass arguments to a Node.js application, and these arguments can be accessed within the application via the `` process.argv `` array.

The first element of the ``process.argv`` array will always be a file system path pointing to the ``node`` executable. The second element is the name of the JavaScript file that is being executed. And the third element is the first argument that was actually passed by the user.

A simple Node script that prints all of the command line arguments passed to the application, along with their index:

````javascript
'use strict';

for (let j = 0; j < process.argv.length; j++) {
    console.log(j + ' -> ' + (process.argv[j]));
}
````

All this script does is loop through the process.argv array and prints the indexes, along with the elements stored in those indexes. It's very useful for debugging if you ever question what arguments you're receiving, and in what order.

````linux 
$ node processargv.js tom jack 43 
````

prints (as example):


````linux
0 -> /home/labber/.nvm/versions/node/v12.22.7/bin/node 1 -> /home/labber/lighthouse/focal/processargv.js

2 -> tom

3 -> jack

4 -> 43
````