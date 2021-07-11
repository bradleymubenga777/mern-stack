# Express Router
Instead of having all our route handlers in our index file, we can seperate in into a different folder and file for convince and better file structure.

```
// Api.js - in router folder
    
// Initilize router
const express = require('express);
const router = express.Router();


// Get All Members
router.get('/', (req, res) => {
    res.json(members)
});

//Get Single Member
router.get('/:id), (req, res) => {
    // If the id is a intiger we have to use parseInt because json data is formated as strings.
    //We have to check igf there is a memeber or not, then send the right http request.
    const found = memebers.some(member => member.id === parseInt(req.params.id))

    if (found) {
        res.json(members.filter(member => member.id === parseIntreq.params.id))
    }

    else {
        res.status(400).json({msg: `No member with the id of ${req.params.id}});newMembe
    }
}


module.exports = router;
```

```
// App.js - Our index file

// We put this in place of the router handlers. Since we have the route specified in the app.use() we dont't have to specify the full route in our route handlers, only query parameters
app.use('/api/members', require('./routes/api/members'))
```