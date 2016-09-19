# Notes

## Module Overview

* About Node
* Setting up your environment
* First Node application
* Node Package Manager (NPM)

## Node MVA Github Repo

[Github link](https://github.com/sayar/NodeMVA)

## What is Node?

* Node.js is a runtime environment and library for running JavaScript applications outside the browser.
* Node.js is mostly used to run real-time server applications and shines through its performance using non-blocking I/O and asynchronous events.

## About Node

* Leverage skills with JavaScript now on the server side
* Unified development environment/language
* High Performance JavaScript Engines - V8
* Open source, created in 2009 by Ryan Dahl
* Windows, Linux, Mac OSX
* Still in "beta" phase

## When to use Node

* Node is great for streaming or event-based real-time applications like:
	* Chat Applications
	* Real time applications and collaborative environments
	* Game Servers
	* Ad Servers
	* Streaming Servers
* Node is great for when you need high levels of concurrency but little dedicated CPU time.
* Great for writing JavaScript code everywhere!

## Node in the Wild

* Microsoft
* Yahoo!
* LinkedIn
* eBay
* Dow Jones
* Cloud9
* The New York Times
* etc.

## The Node Community

* Five years after its debut, Node is the third most popular project on GitHub.
* Over 2 million downloads per month.
* Over 20 million downloads of v0.10x.
* Over 81,000 modules on npm.
* Over 475 meetups worldwide talking about Node.
* Reference: [infographic](http://strongloop.com/node-js/infographic)

## Installing Node on Windows

* [nodejs.org](http://nodejs.org/) - pre-compiled Node.js binaries to install
* [GitHub Install](https://github.com/joyent/node/wiki/Installation) - building it yourself
* Via Chocolatey - package manager for Windows: `choco install nodejs.install`

## Path Variable

* Double check that the node executable has been added to your PATH system environment variable
* [Youtube link](https://www.youtube.com/watch?v=W9pg2FHeoq8) to see how to change your environment variables on Windows
* You will want to make sure the following folder has been added to the PATH variable: `C:\Program Files(x86)\nodejs\`

## Event Driven Programming

"A programming paradigm in which the flow of the program is determined by events such as user actions (mouse clicks, key presses) or messages from other programs." - Wikipedia

## Node Event Loop

* Node provides the event loop as part of the language.
* With Node, there is no call to start the loop.
* The loop starts and doesn't end until the last callback is complete.
* Event loop is run under a single thread; therefore, sleep() makes everything halt.

## Blocking I/O

```javascript
var fs = require('fs');

var contents = fs.readFileSync('package.json').toString();
console.log(contents);
```

