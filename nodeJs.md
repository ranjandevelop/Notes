# What is NodeJs?
NodeJs server-side scripting which ise used to build scalable programs. It is a web application framework built on google Chrome's JavaScript ENgine. It runs within the NodeJs runtime on Mac OS, Windows, and Linux with no changes. This runtime facilities you to execute a JavaScript code on any machine outside a browser.

# What are the advantages of NodeJs?
Following are the main advantages of NodeJs:
- NodeJs is asynchrounus and event-driven. All API's of NodeJs library are non-bloaking, and its server doesn't wait for an API to return data. It moves to the next API after calling it, and a notification mechanism of Events of NodeJs responds to the server from the previous API cal.
- NodeJs is very fast ebcause it builds on Google Chrome's V8 JavaScript engine. Its library is very fast in code execution.
- NodeJs is single threaded but highly scalable.
- NodeJs provides a facility of no buffering. Its application never buffers any data. It outputs the data in chunks.

# Explain NodeJs web application architecture?
A web applicataion distinguishes into 4 layers:
- CLient Layer: The client layer contains web browsers, mobile browsers or applicataions which can make an HTTP request to the web server.
- Server Layer: The Server layer contains the Web Server WHich can intercept the request made by clients an pass them the response.
- Business Layer: The business layer contains application server which is utilized by the web server to do required processing. htis layer interects with data layer via database or some external programs.
- Data Layer: The Data layer contains databases or any source of data.

# What do you understand by the term I/O?
The term I/O stands for input and output. It is used to access anything outside of your application. The I/O describes any program, operation, or device that transfers data to or from a medium or another medium. This medium can be a physical device network, or files within a system.
I/O is loaded into the machine memory memory ti run the program onece application starts.

# Explain the working of NodeJs?
The workflow of a NodeJs web server.
- The clients send requests to the webserver to interact with the web application. These request can be non-blocking or blocking nd used for quertying the data, deleting data, ot updating the data.
- js recieves the incoming requests and adds those to the events Queue
- After this step, the requests are passed one by one through th event loop. It checks if the request are simple enough not to rquire any external resources.
- The event loop then processes the simple requests (non-blocking operations), such as I/O Polling, and retuen the responses to the corresponding clients.
- A single thread fron the thread Pool is assigned to a single comples request. This thread is reponsible for completing particular blocking request by accessing external resources, such as computatioin, database, file system, etc.
- Once the task is copleted, the repsonse is ent to the Event Loop that sends that response back to the client.

# Why is NodeJs Single-Threaded?
NodeJs is a single-threaded application with event looping for async processing. THe biggest advantage of doing async processing on as single thread under typical web load is that you can achieve more performance and scalability than the typical thread-based implementation.

# How is NodeJs better than other most popular frameworks?
Based on the following criteria, we can say that NodeJs is better than other most popular frameworks:
- js makes development simple beacause of its non-bloacking I/O and event-based model. This simplicity results in short response time and concurrent processing, wnlike other frameworks wher developers use thread management.
- js runs on a chrome V8 engine whihc is written in C++. It enhances its performance highly with constant improvement.
- With NodeJs, we will use javascript in both the frontend and backend development that will be much faster.
- js provides sample libraries so that we don;t need to reinvent the wheel.

# In which types of applications is NodeJs most frequently used?
NodeJs is most frequently and widely used in the following applications:
- Internet of Things
- Real-time collaboration tools
- Real-time chats
- Complex SPAs (Single-Page Applications)
- Streaming applications
- Microservices archotetcture etc.

# What are buffers in NodeJs?
In general a buffer is a temporary memory mainly used by the stream to old on to some data until it is consumed. Buffers are used to represent a fixed-size chunk of memory allocated outside of the V8 Javascript engine. It can't be resized. It is like an array of integers, which each represents a byte of data. It is implemented by NodeJs Buffer Class. Buffers also support legact enccodings like ASCII, utf-8etc.

# What is error-first callback?
Error-first callbacks are used to pass errors and data. If something goes wrong, the programmer has to check the first argument because it is always an error argument additional arguments are used to pass data.

# What is an asynchronus API?
All the API's of NodeJs library are asynchronous means non-blocking. A NodeJs based server never waits for an API to return data. The NodeJs server moves to the next API after calling it, and a notification mechanism of Events of NodeJs reponds to the server for the previous API call.

# How can you avoid callbacks?
To avoid callbacks, you can use any one of the following options:
- You can use modularization. It breaks callbakcs into independent functions.
- You can use promise.
- You can use yield with Generatioins and Promises.

# Does NodeJs provide Debugger?
Yes, NodeJs provide a simple TCP based protocal and built-in debugging client. For debugging your Javascript file, you can use debug argument followed by the js file name you want to debug.
```
node debug [script.js | -e "script" | <host>:<port>]
```

# Example to demostrate async await in NodeJs?
```javascript

function wait (timeout) {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve()
        }, timeout);
    });
}

async function requestWithRetry (url) {
    const MAX_RETRIES = 10;
    for(let i = 0; i <= MAX_RETRIES; i++) {
        try {
            return await request(url);
        } catch (err) {
            const timeout = MAth.pow(2, i);
            console.log('Waiting', timeout, 'ms');
            await wait(timeout);
            console.log('Retrying', err.message, i);
        }
    }
}

```

# What are the modules in NodeJs? Which are the different modules used in NodeJs?
In NodeJs applications, modules are like Javscript libraries and include a set of functions. To include a module in a NodeJs application, we must use the require() function with the parenthesis containing the modules's name.
NodeJs has several modules which are used to provide the basic functionality needed for a web application. Following is a list of some of them:
- HTTP
The HTTP modules includes classes, mehtods, and events to create a NodeJs HTTP server.
- util
The util modules includes utility functions required in the application and is very useful for developers.
- url
The url modules is used to include the methods for URL parsing.
- fs
The fs module includes events, classes, and methods to handle the file I/O operations.
- stream
The stream modules is used to include the methods to handle streaming data.
- query string
The query string module is used t include the methods to work with q query string.
- zlib
The zlib module is used to include the methods to compress or decompress the files used in and application.

# What  are buffers in NodeJs?
In general, a buffer is a temporary memory mainly used by the stream to hold on to some data until it is consued. Buffers are used to represent a fixed-size chunk of memory allocated outside of the V8 JavaScript engine. It can't be resized. It is like an array of integers, which each represents a byte of data. Itt is implemented by th nodeJs Buffer class. Buffers also support legacy encoding like ASCII, utf-8, etc.

# What is an asynchronus API?
All the API's of NodeJs library are asynchronus means non-blocking. A NodeJs based server never waits for an API to return data. The NodeJs server moves to the next API after calling it, and a notification mechanism of evnts of NodeJs responds to the server for the previous API call.

# What is REPL in NodeJs?
REPL stands for Read Eval Print Loop. It specific a computer enviroment like a window console or Unix/Linux shell where you can enter a command, and the computer responds with an output. It is very useful in writing and debugging the codes. REPL enviroment incorporates NodeJs.

# Does NodeJs suports cryptography?
Yes, NodeJs crypto modules supports cryptography. It provides cryptographic functionality that includes a set of wrappers for open SSL's hasHMAC, cipher, decipher, sign and verify functions, i.e.
```javascript

const crypto = require('crypto');
const secret = 'abcdefg';
const hash = crypto.createHmac('sha256', secret)
                .update('Welcome')
                .digest('hex);
console.log(hash);

```

# What is npm? What is the main functionality of npm?
npm stands for Node Package Manager. Following are the twomain functionalities of npm:
- Online repositories for nodeJs packages/modules which are searchable on search.nodejs.org
- Command line utility to install packages, do version management and dependency management of NodeJs packages.

# What is the differnce between operational and programmer errors?
Operational errors are not bugs, but create problems with the system like request timeout or hardware failure. On the other hand, programmer errors are actual bugs.

# What is the difference between the global installation of dependencies and local installation of dependencies?
- Global Installation of dependencies is tores in /npm directory. While local installation of dependencies stores in the local mode. Here local mode refers to the package installation in node_modules directory lying in the older where Node application is present.
- Glabally deployed packages cannot be imported using require() in Node application directly. On the other hand, locally deployed packages are accessible via require().
- To install a Node project globally -g flag is used.
```cmd

C:\Nodejs_Workspace> npm install express -g

```
- To install a Node project locally, the syntax is:
```cmd

C:\Nodejs_Workspace> npm install express

```

































































