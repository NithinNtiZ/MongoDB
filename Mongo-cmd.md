# Create user with role
```bash
db.createUser( { user: "nithin", pwd:  "1234", roles: [ role: "readWrite","dbAdmin","dbAdminAnyDatabase","clusterAdmin", db: "test"]});
```
```bash
db.createUser({user: "one",pwd : "1234",roles: [{ role: "read", db: "test" }]})
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