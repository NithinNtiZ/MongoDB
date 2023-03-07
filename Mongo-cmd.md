# create user with role
```bash
db.createUser( { user: "nithin", pwd:  "1234", roles: [ role: "readWrite","dbAdmin","dbAdminAnyDatabase","clusterAdmin", db: "test"]});

db.createUser({user: "one",pwd : "1234",roles: [{ role: "read", db: "test" }]})
```
# Grante role to user
```bash
db.grantRolesToUser('one', ['readWrite']);
```
# Get user details
```bash
db.getUser("nithin")
```
# Delete user
```bash
db.dropUser("nithin")
```
# Other commands
```bash
show dbs
show users
use
db
```