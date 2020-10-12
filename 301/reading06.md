reading notes on: 
https://www.sitepoint.com/an-introduction-to-node-js/
By James Hibbard
JavaScript
February 16, 2020

# What is Node
  Node.js® is a JavaScript runtime built on Chrome’s V8 JavaScript engine.
  Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses
  Google’s V8 JavaScript engine and libuv library.
  
  ## V8 JavaScript Engine
    the open-source JavaScript engine that runs in Google Chrome and other 
    Chromium-based web browsers, including Brave, Opera, and Vivaldi
    compiles JavaScript directly to native machine code 
    V8 engine with various features, such as a file system API, an HTTP library,
    and a number of operating system–related utility methods
    Node.js is a program we can use to execute JavaScript on our computers 
    (ie it’s a JavaScript runtime)
    
  ## Installation
  
  ### Node Binaries vs Version Manager
    go to https://nodejs.org/en/download/
    and grab the Node binaries for your system
    use a version manager: allows you to install multiple versions of Node 
    and switch between them
    https://www.sitepoint.com/quick-tip-multiple-versions-node-nvm/
    go here to learn more about version manager installation
    
  ### “Hello, World!” the Node.js Way
    1. check that Node is installed on your system by opening a terminal 
       and typing 'node -v'
       current LTS version:v12.14.1
    2. create a new file hello.js
       console.log("Hello, World!");
       (in terminal) run the example with: node hello.js
  ### Node.js in Modern JavaScript
      excellent support for ECMAScript 2015 (ES6) and beyond
      you can write your JavaScript using the latest and most modern syntax
      don't worry about compatibility issues
      
      makes use of several modern JavaScript features, such as tagged template
      literals, object destructuring and Array.prototype.flatMap()
      'function upcase(strings, ...values) {
          return values.map(name => name[0].toUpperCase() + name.slice(1))
            .join(' ') + strings[2];
        }

        const person = {
          first: 'brendan',
          last: 'eich',
          age: 56,
          position: 'CEO of Brave Software',
        };

        const { first, last } = person;
        const emoticon = [ ['┌', '('], ['˘', '⌣'], ['˘', ')', 'ʃ'] ];

        console.log(
          upcase`${first} ${last} is the creator of JavaScript! ` + emoticon.flat().join('')
      );'
      save code in node using: 'node index.js'
