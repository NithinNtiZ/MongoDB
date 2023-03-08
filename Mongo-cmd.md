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


# create collection 
```bash
db.createCollection{"movies"}
db.movies.insert({"a":"b", "cast": ["a","b",""c]}) 
``` 
# add new to collection 
```bash
db.movies.update({"a":"b"}.{$set:{"r":"l"}})
```
# remove from collection
```bash
db.movies.update({"a":"b"}.{$unset:{"r":""}}) 	
```
# condition queries 
```bash
db.movies.find({"value": {$gt,$lt: 2000}}).pretty()
```
# This will not show vlaue field
```bash
db.moves.find({}, {"value":0}).pretty()
```
# This will show vlaue field
```bash
db.moves.find({}, {"value":1}).pretty()
```
# This will now show vlaue field but show time field 
```bash
db.moves.find({}, {"value":0 , "time":1}).pretty()
```
# show collection 
```bash
db.mobies.find().pretty()
```				
# delete collection
```bash
db.movies.drop()
```
# Count documents
```bash
db.movies.count()
```
# Document stats
```bash
db.movies.stats()
```
# Selective Delete documents
```bash
db.movies.deleteMany({"value": {$gt: 1000}})
```
# Delete all documents
```bash
db.movies.deleteMany({})
```