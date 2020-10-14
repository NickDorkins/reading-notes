# Read 06 - Node, Express, API's
 
## What Is Node.js?
 
**Node.js is a JavaScript runtime built on Chrome’s V8 JavaScript engine.**
 
>Stackoverflow Definition:
> 
>*Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google's V8 JavaScript engine and libuv library. It is used for developing applications that make heavy use of the ability to run JavaScript both on the client, as well as on server side and therefore benefit from the re-usability of code and the lack of context switching.*
 
`node.js` is often used for developing applications that rely on the ability to run `javascript` both on the client and server side.
 
>Running the same language on both the client and the server benefits from improved code reusability and the less context switching.
 
- **non-blocking** – if one task stalls or pauses for an I/O operation, another can take over while it is idle.
 
>Allows for high efficiency as the program as a whole never has to idle and wait for one task to finish.
 
**Applications that can be written using Node.js include, but are not limited to**:
 
- Static file servers
- Web Application frameworks
- Messaging middleware
- Servers for HTML5 multi player games, or streaming audio/video
- Real time applications
- Cross-platform programs
 
**When asking questions about Node.js, you should**:
 
- Make sure to check the official [API documentation](https://nodejs.org/docs/latest/api/index.html) before asking, your question might be trivial.
- Isolate the problem and reproduce it with as little code as possible.
- If the question has nothing to do with anything that's `node.js` specific, please consider asking it as a `javascript` question instead.
- Mention which version of Node.js you are running. When in doubt, use `node -v` or `node --version`.
- Make sure to only use the `node.js` tag, since `node` is ambiguous.
 

**Interesting Questions and Answers**
 
- [What is Node.js?](https://stackoverflow.com/questions/1884724/what-is-node-js)
- [Templating Engines for Node.js](https://stackoverflow.com/questions/1787716/is-there-a-template-engine-for-node-js)
- [How do I get started with Node.js](https://stackoverflow.com/questions/2353818/how-do-i-get-started-with-node-js)
 
**Tutorials, Guides and Books**
- [Node Tuts](http://nodetuts.com/index.html) (Video Tutorials)
- [Node Beginner](http://www.nodebeginner.org/)
- [Node.js app using Windows Azure](https://www.windowsazure.com/en-us/develop/nodejs/tutorials/web-app-with-express/)
- [Node Manual](https://github.com/mattpardee/nodemanual.org) (One source for API, Node.js Guide and Mozilla's JavaScript reference. Code examples run in [Cloud 9 IDE](http://c9.io/))
- [NodeCasts](http://nodecasts.net/) (Free screencasts)
- [Getting Started with Node.js on Heroku](https://devcenter.heroku.com/articles/getting-started-with-nodejs)
- [Error Handling in Node.js](https://www.joyent.com/developers/node/design/errors)
- [NodeSchool.io](http://nodeschool.io/)
- [Stream Handbook](https://github.com/substack/stream-handbook) (How to write node programs with streams)
- [Pirple - The Node.js Master Class](https://www.youtube.com/watch?v=H9fg7GFagF4&list=PLgTkNlNsy9gXGyou9cT19ySTzLyHWkw9-)
- [Learn Node](https://learnnode.com/)
 
## What is Chrome's V8 JavaScript Engine?
 
[The V8 engine](https://v8.dev/) is the open-source JavaScript engine that runs in Google Chrome and other Chromium-based web browsers, including Brave, Opera, and Vivaldi. It was designed with performance in mind and is responsible for compiling JavaScript directly to native machine code that your computer can execute.
 
> Node programs are not executed in the browser, rather the V8 engine has been enhanced with various features such as:
> - file system API
> - HTTP library
> - a number of operating system–related utility methods
 
## Node Binaries vs Version Manager
 
***Use a version manager it allows you to install multiple versions of Node and switch between them at will.***
 
> There are various advantages to using a version manager. For example, it negates potential permission issues when using Node with `npm` and lets you set a Node version on a per-project basis.
 
>If you are going to use version manager, consult this link: [Install Multiple Versions of Node.js using nvm](https://www.sitepoint.com/quick-tip-multiple-versions-node-nvm/)
 
## Node.js Has Excellent Support for Modern JavaScript
 
[Compatibility Table](https://node.green/)
 
If you’re only targeting one runtime (a specific version of the V8 engine), you can write your JavaScript using the latest and most modern syntax. It also means that you don’t generally have to worry about compatibility issues — as you would if you were writing JavaScript that would run in different browsers.
 
### Example:
```
function upcase(strings, ...values) {
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
);
```
> This example makes use of several modern JavaScript features, such as tagged [template literals](https://www.sitepoint.com/understanding-ecmascript-6-template-strings/), [object destructuring](https://www.sitepoint.com/preparing-ecmascript-6-destructuring-assignment/) and [Array.prototype.flatMap()](https://thecodebarbarian.com/whats-new-in-es2019-flat-flatmap-catch.html#arrayflat-and-arrayflatmap)
 
>> Save this code to a file called index.js and run it from your terminal using the command node index.js. You should see `Brendan Eich is the creator of JavaScript! ┌(˘⌣˘)ʃ` output to the terminal.
 
## Introducing npm, the JavaScript Package Manager
 
***In addition to being the package manager for JavaScript, npm is also the world’s largest software registry. There are over 1,000,000 packages of JavaScript code available to download, with billions of downloads per week.***
 
## Installing a Package Globally
 
Open your terminal and type the following:
 
```
npm install -g jshint
```
 
This will install the [jshint package](https://www.npmjs.com/package/jshint) globally on your system.
 
>You must already have an `index.js` file created for this command to reference
 
```
jshint index.js
```
 
You should now see a number of ES6-related errors. If you want to fix them up, add `/* jshint esversion: 6 */` to the top of the `index.js` file, re-run the command and linting should pass.
 
Refresher: [A Comparison of JavaScript Linting Tools](https://www.sitepoint.com/comparison-javascript-linting-tools/)
 
## Installing a Package Locally
 
You can install packages locally to a repo, as opposed to globally, on your machine. 
 
Create a test folder and open a terminal in that directory. 
 
### Next type this:
 
```
npm init -y
```
 
>This will create and auto-populate a `package.json` file in the same folder. 
 
Next, use npm to install the [lodash package](https://www.npmjs.com/package/lodash) and save it as a project dependency:
 
```
npm install lodash --save
```
 
Create a file named `test.js` and add the following:
 
```
const _ = require('lodash');
 
const arr = [0, 1, false, 2, '', 3];
console.log(_.compact(arr));
```
 
Finally, run the script using `node test.js`. You should see `[ 1, 2, 3 ]` output to the terminal.
 
## Working with the `package.json` File
 
In the test.js file:
> If you open the `package.json` file, you’ll see lodash listed under the `dependencies` field. By specifying your project’s dependencies in this way, you allow any developer anywhere to clone your project and use npm to install whatever packages it needs to run.
 
Reference Link: [A Beginner’s Guide to npm — the Node Package Manager](https://www.sitepoint.com/beginners-guide-node-package-manager/)
 
## What Is Node.js Used For?
 
Articles covering build tooling on SitePoint:
 
- [A Beginner’s Guide to Webpack](https://www.sitepoint.com/webpack-beginner-guide/)
- [Up and Running with ESLint — the Pluggable JavaScript Linter](https://www.sitepoint.com/up-and-running-with-eslint-the-pluggable-javascript-linter/)
- [An Introduction to Gulp.js](https://www.sitepoint.com/introduction-gulp-js/)
- [Unit Test Your JavaScript Using Mocha and Chai](https://www.sitepoint.com/unit-test-javascript-mocha-chai/)
 
> If you want to start developing apps with any modern JavaScript framework, you’ll be expected to have a working knowledge of Node and npm (or maybe [Yarn](https://www.sitepoint.com/yarn-vs-npm/)). This isn’t because you need a Node back end to run these frameworks. Rather, it’s because these frameworks (and related packages) are all available via npm and rely on Node to create a sensible development environment in which they can run.
 
Reference Link: [The Anatomy of a Modern JavaScript Application](https://www.sitepoint.com/anatomy-of-a-modern-javascript-application/)
 
## Node.js Lets Us Run JavaScript on the Server
 
- In 1994 NetScape was the first to attempt to run JavaScript on a server.