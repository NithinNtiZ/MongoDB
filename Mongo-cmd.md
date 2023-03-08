# Create Collection & Document & Users

# Create user with role
```bash
db.createUser( 
    { user: "nithin",  
      pwd:  "1234",  
      roles: [ role: "readWrite","dbAdmin","dbAdminAnyDatabase","clusterAdmin", db: "test"]})  
```
```bash
db.createUser(
    {user: "one",  
     pwd : "1234",  
     roles: [{ role: "read", db: "test" }]})  
```
----
# Grant role to user
```bash
db.grantRolesToUser('one', ['readWrite']);
```
---
# Get user details
```bash
db.getUser("nithin")
```
---
# Delete user
```bash
db.dropUser("nithin")
```
---
# Other commands
```bash
show dbs
show users
use
db
```
# MongoDB compass connection string

```bash
mongodb://192.168.1.1:27017,192.168.1.2:27018,192.168.1.3:27019?replicaSet=myReplicaset
```


# Create Collection 
```bash
db.createCollection{"movies"}
db.movies.insert({"a":"b", "cast": ["a","b",""c]}) 
``` 
# Add New To Collection 
```bash
db.movies.update({"a":"b"}.{$set:{"r":"l"}})
```
# Remove From Collection
```bash
db.movies.update({"a":"b"}.{$unset:{"r":""}}) 	
```
# Condition Queries 
```bash
db.movies.find({"value": {$gt,$lt: 2000}}).pretty()
```
# This will Not Show Value Field
```bash
db.moves.find({}, {"value":0}).pretty()
```
# This Will Show Value Field
```bash
db.moves.find({}, {"value":1}).pretty()
```
# This Will Now Show Value Field But Show time field 
```bash
db.moves.find({}, {"value":0 , "time":1}).pretty()
```
# Show Collection 
```bash
db.mobies.find().pretty()
```				
# Delete Collection
```bash
db.movies.drop()
```
# Count Documents
```bash
db.movies.count()
```
# Document Stats
```bash
db.movies.stats()
```
# Selective Delete Documents
```bash
db.movies.deleteMany({"value": {$gt: 1000}})
```
# Delete All Documents
```bash
db.movies.deleteMany({})
```