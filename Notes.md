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

## Callback Style Programming

* Event loops result in callback-style programming where you break apart a program into its underlying data flow.
* In other words, you end up splitting your program into smaller and smaller chunks until each chunk is mapped to an operation with data.
* Why? So that you don't freeze the event loop on long-running operations (such as disk or network I/O).

## Callback Insanity

```javascript
var fs = require('fs');

fs.readdir('.', function (err, files) {
	if (err) {
		console.log('Error finding files: ' + err);
	} else {
		files.forEach(function (filename, fileIndex) {
			console.log(filename);
			gm(source + filename).size(function (err, values) {
				if (err) {
					console.log('Error identifying file size: ' + err);
				} else {
					console.log(filename + ' : ' + values);
					aspect = (values.width / values.height)
					widths.forEach(function (width, widthIndex) {
						height = Math.round(width / aspect);
						console.log('resizing ' + filename + ' to ' + height + ' x ' + height);
						this.resize(width, height).write(destination + 'w' + width + '_' + filename, function (err) {
							if (err) {
								console.log('Error writing file: ' + err);
							}
						});
					}.bind(this));
				}
			});
		});
	}
});
```

## Promises

* A promise will return a promise for an object in the future.
* Promises can be chained together.
* Simplify programming of async systems.

[Read More](http://spin.atomicobject.com/2012/03/14/nodejs-and-asynchronous-programming-with-promises/)

## What is NPM?

* Official package manager for Node.
* Bundled and installed automatically with the environment.

Frequent Usage:
* `npm install --save package_name`
* `npm update`

## What is a package.json?

```javascript
{
	"name": "Node101",
	"version": "0.1.0",
	"description": "MVA Presentation Code",
	"main": "1_hello_world.js",
	"author": {
		"name": "Rami Sayar",
		"email": ""
	}
}
```

## Popular NPM Modules

**Most Depended Upon**
* 7053 underscore
* 6458 async
* 5591 request
* 4931 lodash
* 3630 commander
* 3543 express
* 2708 optimist
* 2634 coffee-script

## How does it work?

* Reads package.json
* Installs the dependencies in the local node_modules folder
* In global mode, it makes a node module accessible to all.
* Can install from a folder, tarball, web, etc...
* Can specify dev or optional dependencies.

## Resources

* [Callbacks are imperative promises are functional nodes biggest missed opportunity](https://blog.jcoglan.com/2013/03/30/callbacks-are-imperative-promises-are-functional-nodes-biggest-missed-opportunity/)
* [Using nodes event module](http://code.tutsplus.com/tutorials/using-nodes-event-module--net-35941)
* [Node.js and asynchronous programming with promises](http://spin.atomicobject.com/2012/03/14/nodejs-and-asynchronous-programming-with-promises/)
* [GitHub repo](https://github.com/sayar/NodeMVA)

## Module Overview

* What is Express?
* Installing & Using Express
* Demo: Creating a simple REST API
* Templating

## What is Express?

* Express is a minimal, open source, and flexible node.js web app framework designed to make developing websites, web apps, and APIs much easier.

## Why use Express?

* Express helps you respond to requests with route support so that you may write responses to specific URLs.
* Supports multiple templating engines to simplify generating HTML.

## Installing and Using Express

```
npm install express
npm install jade
```

## Explanation of Routes

* A router maps HTTP requests to a callback.
* HTTP requests can be sent as GET/POST/PUT/DELETE, etc.
* URLs describe the location targeted.
* Node helps you map a HTTP GET request like: `http://localhost:8888/index`
* To a request handler (callback)

```javascript
app.get('/index', function (req, res) {});
```

