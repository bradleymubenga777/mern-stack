# Middleware
Middleware allow us to run functions everytime routes are visted. In order to use middleware we create our middleware in a folder, and then use the ``app.use()`` method to use it and we initialize it above the route handlers.

```
// Logger.js -  in middleware folder
const logger = (req, res, next) => {
    //This uses the request object to give us the http
    console.log(`${req.protocol}`)

    //This is allows the server to continue with other middleware
    next()
};

module.exports = logger;
```

```
// App.js - server index file

const express = require('express');
// Using the middleware as module
const logger = require('./Logger.js');

const app = express();

//Initilize Middleware
app.use(logger)

app.get('/', (req, res) => {
    res.send("Hello World")
});

app.listen(5000);
```