# How to create NodeJS apps
Little guide to create NodeJS apps <b>from scratch</b>.

### Step 1: Download and Install
<b>1.</b> Go to the node webpage and [download it!](https://nodejs.org/en/download/) </br>

<b>2.</b> Install node </br>

<b>3.</b> Check if the it's installed through npm package version </br>
```sh
   $ npm --v
```

### Step 2: [Create a Local Repo from Scratch](https://github.com/sharkb8i/how-to-create-repos/)

### Step 3: Starting the Project
<b>1.</b> Open the <b>cmd</b> </br>

<b>2.</b> Go into the local repo directory </br>
```sh
   $ cd project-repo-name
```

<b>3.</b> Start the project </br>
```sh
   $ npm init
```
<i><b>TIP: </b>Let the standard creation by pressing ENTER and finally type 'yes'.</i>

### Step 4: Create the Entry Pointe File
<b>1.</b> Open the [VS Code](https://code.visualstudio.com/download) </br>

<b>2.</b> Create a blank entry point file (<b>index.js</b>) </br>

### Step 5: Install Express
<b>1.</b> Go to the <b>cmd</b> again and install <b>express</b> dependency </br>
```sh
   $ npm install --save express
```
<i><b>TIP: </b>The argument '--save' is to add to the project.</i>

### Step 6: Create a Server (Example)
<b>1.</b> Into the <b>index.js</b> file: </br>
```js
   const http = require('http');
   
   const hostname = '127.0.0.1';
   const port = 3000;            // in a programming environment is different
   
   const server = http.createServer( (req, res) => { 
      res.statusCode = 200;
      res.setHeader('Content-Type', 'text/plain');
      res.end('Hello World!');
   });
   
   server.listen(port, hostname, () => {    // to open the localhost page
      console.log("Server is running!");
   });
```

### Step 7: Execute the Server
<b>1.</b> Open the <b>cmd</b> </br>

<b>2.</b> Execute the server </br>
```sh
   $ node index.js
```

<b>3.</b> From now the code is running on <i>localhost:3000</i> </br></br>

### BONUS: How to render an HTML page (Example)
<b>1.</b> Open the [VS Code](https://code.visualstudio.com/download) </br>

<b>2.</b> Create a html file(<b>index.html</b>) and edit </br></br>
<b>index.html</b> </br>
```html
   <h2>Hello World!!!<h2>
```
<b>index.js</b> </br>
```js
   const express = require('express');
   const app = express();
   const path = require('path');
   const router = express.Router();       // define routes
   
   // localhost:3000
   router.get('/', function(req, res) {   // what will be rendered on this '/' route
      res.sendFile(path.join(__dirname+'/index.html'));  // what will be executed
   });
   
   // localhost:3000/about
   router.get('/about', function(req, res) {   // what will be rendered on this '/' route
      res.sendFile(path.join(__dirname+'/about.html'));  // what will be executed
   });
   
   app.use('/', router);
   app.listen(process.env.port || 3000);  // run on standard port or on 3000
   
   console.log("Server is running!");
```
<b>cmd</b> </br>
```sh
   $ node index.js
```
