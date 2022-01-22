<<<<<<< HEAD
# Steps to implement Swagger to a Spring boot application

As this repository is based in the calls to an API a good practice is the integration of a tool, as swagger, to create the documentation needs to
know how to make the calls, the response, the expected json structure, etc, so this file is to show how can we implement
Swagger in our Spring application.

## 1. Getting the Swagger Spring dependency

First of all we have to create our [quotes.json](./quotes.json) file where we are going to storage the data, the quotes in our case:

```ruby
{
    "quotes": [
    {
        "id":1,
        "author": "Marcus Aurelius",
        "quote": "Waste no more time arguing what a good man should be. Be One."
    },
    {
        "id":2,
        "author": "Marcus Aurelius",
        "quote": "You could leave life right now. Let that determine what you do and say and think."
    },
    {
        "id":3,
        "author": "Seneca",
        "quote": "He who fears death will never do anything worth of a man who is alive."
    },
    {
        "id":4,
        "author": "Seneca",
        "quote": "Life is very short and anxious for those who forget the past, neglect the present, and fear the future."
    },..

```

## 2. Enable Swagger in our code

We have to create a file where we can set the actions to run our server using the json-server package that we will install in the next step. In this file is where we can set the port and the file to show in the server, as we can see below:

```ruby

const jsonServer = require('json-server');
const server = jsonServer.create();
const router = jsonServer.router('quotes.json');
const middlewares = jsonServer.defaults();
const port = process.env.PORT || 3000;

server.use(middlewares);
server.use(router);

server.listen(port);

```

## 3. Configuring Swagger

Now we have to create an environment where we can use our json as an API in our machine, this way we are going to make sure that we have all the dependencies needed to deploy the app in heroku, the commands that we are going to need are:

Creating the package.json file which is going to have the configuration of out API:

```sh
npm init

```

We are going to need the [package-lock.json](./package-lock.json), so we have to use:

```sh
npm i

```

Installing server, make sure that we can see the dependency in our [package.json](./package.json) file once is installed:

```sh
npm install json-server

```

We have to create a new script in the file to run the server file that we created before like so:

```ruby

  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js"
  }

```

Setting the file to use as endpoint, we can check it in the URL that this command should show us:

```sh
json-server --watch quotes.json

```

## 4. Adding details as annotations to APIs

[Here](https://devcenter.heroku.com/articles/heroku-cli) we can find the way to use it properly in different environments.

If everything worked properly we have to be able of get something like so
[running JSON server](https://stoic-quotes-app.herokuapp.com/).

We have to make sure that in the resources section we can see our json file as endpoint.
=======
# SwaggerAPIdocumentation
Simple Spring project to document the steps to implement Swagger in our application
>>>>>>> e2d59b67b672d8f329407af6c929eee813ffa253
