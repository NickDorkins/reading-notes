# Read: 05 Heroku Deployment
 
Source: [Getting Started on Heroku with Node.js - Heroku Dev Center](https://devcenter.heroku.com/articles/getting-started-with-nodejs#next-steps)
 
Heroku is a Node Package Manager, it is used to deploy apps to the web. Heroku apps are able to be deployed, maintained, and scaled from the terminal.
 
Heroku apps allow the developer to watch traffic and scale their app according the the traffic logs. Scaling is done through utilizing dyno's. Free databases provide the user with one free dyno that turns off after 30-minutes of inactivity and if their app requires more support the user can purchase upgrade packages anywhere from hobby to professional platforms. Upgraded platforms allow the user to add additional dyno's to support the traffic of their application.
 
Inside the root directory of the application there is a `Procfile` that explicitly declares what commands should be executed to start the application.
 
The `Procfile` declares a single process type, web, and the command needed to run it. the name "web" is important as it declares that this process type will be attached to the HTTP stackof Heroku, receiving web traffic when deployed.
 

Heroku recognizes an app as `Node.js` by the existence of a `package.json` file in the root directory. For your own apps, you can create one by running `npm init --yes`.
 
The `package.json` file determines both the version of `Node.js` that will be used to run your application on Heroku, as well as the dependencies that should be installed with your application.
 
The user can also run their Heroku app locally on their machine. 
 
```
$ heroku local web
```
This is similar to running `live-server` on an HTML file on your local machine.
 
Open [Local Host](http://localhost:5000/) in your web browser to see your app running locally.
 
Any modifications that you make on your local test must be pushed locally to save the changes.
 
```
npm install **File Name**
```
 
Thsi will modify and save changes locally, once that is complete you can A.C.P. like normal.
 
## Don't forget that for all new repo's:
 
```
$ git push origin master 
```
 
## Is now
 
```
$ git push origin main
```
 
By default, Heroku stores 1500 lines of logs from your application, however, the user can add on extra provisions to extend the search logs with:
 
```
$ heroku plugins:install heroku-papertrail
```
 
To get a better understanding of how the dyno's work you can run:
 
```
$ heroku run bash 
```
 
Heroku lets you externalize configuration - storing data such as encryption keys or external resource, additional resources can be found at [config vars](https://devcenter.heroku.com/articles/config-vars).
 
At runtime, config vars are exposed as environment variables to the application.
 
You can also add a database to your application.
 
To add the database you can use:
```
$ heroku addons:create heroku-postgresql:hobby-dev
```
To add the dependancies:
```
$ npm install pg
```
To deploy this to Heroku:
```
$ heroku pg:psql
```
 
The [add-on marketplace](https://elements.heroku.com/addons/categories/data-stores) has a large number of data stores, from Redis and MongoDB providers, to Postgres and MySQL.
 
Check out my [GitHub](https://github.com/NickDorkins) to see the extra information that is commented out.
 
## Deploying a Simple Blog to Heroku
Source: [Node.js For Beginners. Deploy Your Blog to Heroku](https://howtonode.org/deploy-blog-to-heroku)




<!-- ## Setup Instructions
 
### Mac instructions:
 
```
brew install heroku/brew/heroku
```
 
```
heroku login
heroku: Press any key to open up the browser to login or q to exit
```
 
> Warning: If browser does not open, visit
> https://cli-auth.heroku.com/auth/browser/***
 
> - heroku: Waiting for login...
> - Logging in... done
> - Logged in as me@example.com
 
This tutorial will work for any version of Node greater than 8 - check that it’s there:
 
```
node --version
v12.16.3
```
 
`npm` is installed with Node, so check that it’s there. If you don’t have it, install a more recent version of Node:
 
```
npm --version
6.14.4
```
 
Now check that you have git installed. If not, install it and test again.
 
```
git --version
git version 2.17.0
```
 
## Prepare the App
 
To clone a local version of the sample application that you can then deploy to Heroku, execute the following commands in your local command shell or terminal:
 
```
git clone https://github.com/heroku/node-js-getting-started.git
cd node-js-getting-started
```
 
> You now have a functioning Git repository that contains a simple application as well as a `package.json` file, which is used by Node’s dependency manager.
 
## Deploy the app
 
Create an app on Heroku, which prepares Heroku to receive your source code.
 
```
heroku create
```
 
> When you create an app, a git remote (called heroku) is also created and associated with your local git repository.
 
> Heroku generates a random name (in this case sharp-rain-871) for your app, or you can pass a parameter to specify your own app name.
 
Now deploy your code:
 
```
git push heroku main
```
 
The application is now deployed. Ensure that at least one instance of the app is running:
 
```
heroku ps:scale web=1
```
 
Now visit the app at the URL generated by its app name. As a handy shortcut, you can open the website as follows:
 
```
heroku open
```
 
## View Logs
 
View information about your running app using one of the logging commands:
 
```
heroku logs --tail
```
 
Visit your application in the browser again, and you’ll see another log message generated.
 
Press `Control+C` to stop streaming the logs.
 
## Define a Procfile
 
 **Procfile** - a text file in the root directory of your application, to explicitly declare what command should be executed to start your app.
 
The Procfile in the example app you deployed looks like this:
```
web: node index.js
```
 
> This declares a single process type, web, and the command needed to run it. The name web is important here. It declares that this process type will be attached to the HTTP routing stack of Heroku, and receive web traffic when deployed.
 
> Procfiles can contain additional process types. 
> 
>For example, you might declare one for a background worker process that processes items off of a queue.
 
## Scale the app
 
Right now, your app is running on a single web dyno. Think of a dyno as a lightweight container that runs the command specified in the Procfile.
 
You can check how many dynos are running using the ps command:
 
```
heroku ps
=== web (Free): `node index.js`
web.1: up 2014/04/25 16:26:38 (~ 1s ago)
```
 
> - By default, your app is deployed on a free dyno. 
>   - Free dynos will sleep after a half hour of inactivity. 
>   - Causes a delay of a few seconds for the first request upon waking. 
>   - Subsequent requests will perform normally. 
>   - Free dynos also consume from a monthly, account-level quota of free dyno hours - as long as the quota is not exhausted, all free apps can continue to run.
 

**To prevent dyno's sleeping you can upgrade the dyno you are using.**
 
- Hobby Dyno
- Professional Dyno
 
> Example: If you migrate your app to a professional dyno, you can easily scale it by running a command telling Heroku to execute a specific number of dynos, each running your web process type.
 
Scaling an application on Heroku is equivalent to changing the number of dynos that are running. Scale the number of web dynos to zero:
 
```
heroku ps:scale web=0
```
 
> Access the app again by hitting refresh on the web tab, or heroku open to open it in a web tab. You will get an error message because you no longer have any web dynos available to serve requests.
 
Scale it up again:
 
```
heroku ps:scale web=1
```
 
> For abuse prevention, scaling a non-free application to more than one dyno requires account verification.
 
## Declare app dependencies
 
*Heroku recognizes an app as Node.js by the existence of a `package.json` file in the root directory. For your own apps, you can create one by running `npm init --yes`.*
 
The demo app deployed already has a `package.json`, and it looks something like this:
 
```
{
  "name": "node-js-getting-started",
  "version": "0.3.0",
  ...
  "engines": {
    "node": "12.x"
  },
  "dependencies": {
    "ejs": "^2.5.6",
    "express": "^4.15.2"
  },
  ...
}
```
 
The `package.json` file determines both the version of `Node.js` that will be used to run your application on Heroku, as well as the dependencies that should be installed with your application.
 
Run this command in your local directory to install the dependencies, preparing your system for running the app locally:
 
```
npm install
added 132 packages in 3.368s
```
 
Once dependencies are installed:
- Run your app locally
- A `package-lock.json` file is generated when `npm install` is run
>  Make sure to check this into git. When subsequent dependencies are added, npm will make changes to this file, so be sure to add those changes to git too.
 
When an app is deployed, Heroku reads the `package.json` to install the appropriate node version and the `package-lock.json` to install the dependencies.
 
## Run the app locally
 
Now start your application locally using the heroku local command, which was installed as part of the Heroku CLI:
 
```
heroku local web
[OKAY] Loaded ENV .env File as KEY=VALUE Format
1:23:15 PM web.1 |  Node app is running on port 5000
```
Just like Heroku, heroku local examines the `Procfile` to determine what to run.
 
## Push local changes
 
Begin by adding a dependency for cool-ascii-faces in package.json. Run the following command to do this:
 
```
npm install cool-ascii-faces
+ cool-ascii-faces@1.3.4
added 9 packages in 2.027s
```
 
Modify index.js so that it requires this module at the start. Also add a new route (/cool) that uses it. Your final code should look like this:
 
```
const cool = require('cool-ascii-faces');
const express = require('express');
const path = require('path');
const PORT = process.env.PORT || 5000;
 
express()
  .use(express.static(path.join(__dirname, 'public')))
  .set('views', path.join(__dirname, 'views'))
  .set('view engine', 'ejs')
  .get('/', (req, res) => res.render('pages/index'))
  .get('/cool', (req, res) => res.send(cool()))
  .listen(PORT, () => console.log(`Listening on ${ PORT }`));
  ```
 
Now test locally:
 
```
npm install
heroku local
```
 
Visiting your application at http://localhost:5000/cool, you should see cute faces displayed on each refresh: ( ⚆ _ ⚆ ).
 
Now deploy. Almost every deploy to Heroku follows this same pattern. First, add the modified files to the local git repository:
 
```
git add .
```
 
Now commit the changes to the repository:
 
```
git commit -m "Add cool face API"
```
 
Now deploy, just as you did previously:
 
```
git push heroku main
```
 
Finally, check that everything is working:
 
```
heroku open cool
```
 
You should see another face.
 
## Provision add-ons
 
> By default, Heroku stores 1500 lines of logs from your application. However, it makes the full log stream available as a service - and several add-on providers have written logging services that provide things such as log persistence, search, and email and SMS alerts.
 
Provision the papertrail logging add-on:
 
```
heroku addons:create papertrail
Adding papertrail on sharp-rain-871... done, v4 (free)
Welcome to Papertrail. Questions and ideas are welcome (support@papertrailapp.com). Happy logging!
Use `heroku addons:docs papertrail` to view documentation.
```
 
The add-on is now deployed and configured for your application. You can list add-ons for your app like so:
 
```
heroku addons
```
 
Visit the papertrail console to see the log messages:
 
```
heroku addons:open papertrail
```
 
Your browser will open up a Papertrail web console, showing the latest log events. The interface lets you search and set up alerts:
 
![Example Logs](https://devcenter1.assets.heroku.com/article-images/2105-imported-1443570562-2105-imported-1443555038-pap-1.png)
 
## Start A Console
 
Each dyno has its own ephemeral filespace, populated with your app and its dependencies - once the command completes (in this case, bash), the dyno is removed.
 
```
heroku run bash
Running `bash` attached to terminal... up, run.3052
~ $ ls
Procfile  README.md  package.json  package-lock.json  src  tests
~ $ exit
exit
```
 
If you receive an error, `Error connecting to process`, then you may need to configure your firewall.
 
Don’t forget to type `exit` to exit the shell and terminate the dyno.
 
## Define config vars
 
**Heroku lets you externalize configuration - storing data such as encryption keys or external resource addresses in config vars.**
 
At runtime, config vars are exposed as environment variables to the application.
 
For example, modify index.js so that it introduces a new route, /times, that repeats an action depending on the value of the TIMES environment variable. Under the existing get() call, add another:
 
```
.get('/times', (req, res) => res.send(showTimes()))
```
 
At the end of the file, add the following definition for the new function, showTimes():
 
```
showTimes = () => {
  let result = '';
  const times = process.env.TIMES || 5;
  for (i = 0; i < times; i++) {
    result += i + ' ';
  }
  return result;
}
```
 
> heroku local will automatically set up the environment based on the contents of the .env file in your local directory. In the top-level directory of your project, there is already a .env file that has the following contents:
> 
>>TIMES=2
 
If you run the app with `heroku local`, you’ll see two numbers will be generated every time.
 
To set the config var on Heroku, execute the following:
 
```
heroku config:set TIMES=2
```
 
View the config vars that are set using `heroku config`:
 
```
heroku config
== sharp-rain-871 Config Vars
PAPERTRAIL_API_TOKEN: erdKhPeeeehIcdfY7ne
TIMES: 2
```
Deploy your changed application to Heroku and then visit it by running `heroku open times`.
 
## Provision a database
 
> The [add-on marketplace](https://elements.heroku.com/addons/categories/data-stores) has a large number of data stores, from Redis and MongoDB providers, to Postgres and MySQL. In this step, you will add a free Heroku Postgres Starter Tier dev database to your app.
 
Add the database:
 
```
heroku addons:create heroku-postgresql:hobby-dev
Adding heroku-postgresql:hobby-dev... done, v3 (free)
```
 
> This creates a database, and sets a `DATABASE_URL` environment variable (you can check by running `heroku config`).
 
Use npm to add [node-postgres](https://node-postgres.com/) to your dependencies:
 
```
npm install pg
+ pg@8.1.0
added 16 packages in 4.002s
```
 
```
  "dependencies": {
    "cool-ascii-faces": "^1.3.4",
    "ejs": "^2.5.6",
    "express": "^4.15.2",
    "pg": "^8.1.0"
  },
  ```
 
Now edit your `index.js` file to use this module to connect to the database specified in your `DATABASE_URL` environment variable. Add this near the top:
 
```
const { Pool } = require('pg');
const pool = new Pool({
  connectionString: process.env.DATABASE_URL,
  ssl: {
    rejectUnauthorized: false
  }
});
```
 

Now add another route,` /db`, by adding the following just after the existing `.get('/', ...)`:
 
```
.get('/db', async (req, res) => {
    try {
      const client = await pool.connect();
      const result = await client.query('SELECT * FROM test_table');
      const results = { 'results': (result) ? result.rows : null};
      res.render('pages/db', results );
      client.release();
    } catch (err) {
      console.error(err);
      res.send("Error " + err);
    }
  })
  ```
 
This ensures that when you access your app using the `/db` route, it will return all rows in the `test_table` table.
 
Deploy this to Heroku. If you access `/db` you will receive an error as there is no table in the database. Assuming that you have Postgres installed locally, use the `heroku pg:psql` command to connect to the remote database, create a table and insert a row:
 
```
heroku pg:psql
psql (11.5)
SSL connection (cipher: DHE-RSA-AES256-SHA, bits: 256)
Type "help" for help.
=> create table test_table (id integer, name text);
CREATE TABLE
=> insert into test_table values (1, 'hello database');
INSERT 0 1
=> \q
```
 
Now when you access your app’s /db route, you will see something like this:
 
> ## Database Results
> - 1 - hello database
 
Read more about [Heroku PostgreSQL](https://devcenter.heroku.com/articles/heroku-postgresql).
 
A similar technique can be used to install [MongoDB or Redis add-ons](https://elements.heroku.com/addons/categories/data-stores).
 

## Next steps
 
You now know how to deploy an app, change its configuration, view logs, scale, and attach add-ons.
 
Here’s some recommended reading. The first, an article, will give you a firmer understanding of the basics. The second is a pointer to the main Node.js category here on Dev Center:
 
- Read [How Heroku Works](https://devcenter.heroku.com/articles/how-heroku-works) for a technical overview of the concepts you’ll encounter while writing, configuring, deploying and running applications.
 
- Visit the [Node.js category](https://devcenter.heroku.com/categories/nodejs-support) to learn more about developing and deploying Node.js applications.
 
- Read [Deploying Node.js Apps on Heroku](https://devcenter.heroku.com/articles/deploying-nodejs) to understand how to take an existing Node.js app and deploy it to Heroku. -->