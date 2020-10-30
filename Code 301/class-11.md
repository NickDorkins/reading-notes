# Read: 11 - EJS

Source:[Watch EJS tutorial from WalkThroughCode on YouTube, Videos 1-5](https://www.youtube.com/playlist?list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt)

## Step 1:Overview(Terminal)
```
npm init -y
```

## Step 2:(Terminal)
```
npm install --save express body-parser cors ejs
```

## Step 3:(server.js)
```
// Connect Dependencies
let express = require('express');
let bodyParser = require('body-parser');
let cors = require('cors');
let path = require('path');

let app = express;

app.use(bodyParser());
app.use(cors());

app.set('views', path.join(_dirname, 'views'));

app.set('view engine', 'ejs')

```
> `path` is built in module for node

## Step 4:(Terminal)
- Create a new directory called "views"
- Create a file inside "views" directory called "index.ejs"

## Step 5:(index.ejs)
```
<h1>Hello World</h1>
```
---
## Step 6 Getting started:(server.js)
```
app.get('/', function(request, response){
  response.render('index');
});

app.listen(8000, function() {
console.log("Listening on port 8000")
});
```

## Step 7:(Terminal)
```
node server.js
```
>Should display `"Listening on port 8000"` in terminal
---
## Step 8: Injecting values into the views(server.js)
```
app.get('/', function(request, response){
  response.render('index', {
  foo: 'bar'
  });
});

```
> `response.render` takes 3 parameters:
> - view (string of the file name)
> - Object of local variables
> - Call back

## Step 9:(index.ejs)
```
Before:
<h1>Hello World</h1>

After:
<h1>Hello <%= foo %></h1>
```

## Step 10:(Terminal)
```
nodemon
```
---
## Step 11 For loops and Arrays:(server.js)
```
Before:

app.get('/', function(request, response){
  response.render('index', {
  foo: 'bar'
  });
});
-------------------------------------
After:

app.get('/', function(request, response){
  response.render('index', {
  people: [
    {name: 'dave' },
    {name: 'jerry'},
  ]
  });
});
```

## Step 12:(index.js)
```
<ul>
  <% for(var person of people) { %>
    <li><% person.name%></li>
  <% } %>
</ul>
```
---
## Step 13 if/else statement: (index.js)
```
<ul>
  <% for(var person of people) { %>
    <% if(person.name === 'dave') {
      <li>This is definetly <% person.name%>!!!</li>
        <% } else { %>
      <li>This is definetly NOT <% person.name %>!!! This is <%= person.name %></li>
    <% } %>
  <% } %>
</ul>
```

## Additional resources:
- [Google Books APIs - Working Volumes](https://developers.google.com/books/docs/v1/using#WorkingVolumes)
- [Embedded JavaScript templating](https://ejs.co/)
- [How To Use EJS to Template Your Node Application](https://www.digitalocean.com/community/tutorials/how-to-use-ejs-to-template-your-node-application)
- [Using EJS to template a Node application - scotch-io](https://github.com/scotch-io/node-ejs)