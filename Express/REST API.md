# REST API
Given that we have data stored in json or bson format we can retriece this data and serve it back as a response to this route. The following are exapmles of REST API's that responds in JSON.

```
// Our Data
const memebers = [
    {
        id: 1,
        name: 'Brad'
        email: 'brad@email.com
    },
    {
        id: 1,
        name: 'Mubenga'
        email: 'mubenga@email.com
    }

]
```

```
// Get All Members
app.get('/api/members', (req, res) => {
    res.json(members)
});
```

```
//Get Single Member
app.get('/api/members/:id), (req, res) => {
    // If the id is a intiger we have to use parseInt because json data is formated as strings.
    //We have to check igf there is a memeber or not, then send the right http request.
    const found = memebers.some(member => member.id === parseInt(req.params.id))

    if (found) {
        res.json(members.filter(member => member.id === parseIntreq.params.id))
    }

    else {
        res.status(400).json({msg: `No member with the id of ${req.params.id}});
    }
}
```

```
app.post('/', (req, res) => {
    //MAKE SURE EXPRESS PARSER IS USED AS MIDDLEWARE, OTHERWISE IT WILL NOT WORK!
    const newMember = {
        id: Math.random(1), //Id is supplied by database
        name: req.body.name,
        email: req.body.email
    }

    if (!newNember.name || !newMember.email) {
        return res.status(400).json({msg: 'Please include a name and email})
    }

    //This will be replaced by mongoose's syntax to add to database
    members.push(newMember);
    res.json(members)
})
```

```
```