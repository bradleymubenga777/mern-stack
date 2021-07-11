# Basic Server Syntax
```
// Import Express Module
const express = require('express);

// Inititlize Express App
const app = express.app();

// Create your endpoints/route handlers
app.get('/', (req, res) => {
    res.send('Hello World')
});

// Listen on a port
app.listen(5000)
```

# Basic Route Handling
- Handling requests/routes is simple
- app.get(), app.post(), app.put(), app.delete(), etc.
- Acess to params, query strings, url parts, etc
- Express has a router so we can store routes in separate files and export.
- We can parse incoming data.

## Request Object (req)
The request object represents HTTP properties such as the url parameters, query strings or any dtatsent in the body. We can create middleware to change or add things to this object.

## Response Object (res)
Represents the HTTP response it is on us to either send back JSON data, render a temple or redirect.

# Express Middleware
*Middleware Functions* are functions that have access to the *request* and *response* object. Express has built in middleware but middleware also comes from 3rd party packages as well as custom middleware.

- Execute any code
- Make changes to the request and response objects
- End response cycle
- Call next middleware in the stack