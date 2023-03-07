# STEP:1 - change conf file
### Add following line in node 1 conf file

`conf file:`

```bash
net:
 port: 27017
 bindIp: 192.168.1.238

replication:
 replSetName: myReplicaset
```

# STEP:2 - Start The Service

`LINUX`
```bash
node : 1
mongod --port 27017 --dbpath "/opt/mongo/data" --replSet myReplicaset

node : 2
mongod --port 27018 --dbpath "/opt/mongo/data" --replSet myReplicaset

node : 3
mongod --port 27019 --dbpath "/opt/mongo/data" --replSet myReplicaset
```

`WINDOWS`
 
 ```bash
Start the service
 ```

 # STEP:3 - Login To Any Node

 `node : 1` : 
 ```bash
mongosh mongodb://192.168.1.238:27017
 ```

### Type following commands 
```bash
rs.initiate()
rs.add("192.168.1.236:27018")
rs.add("192.168.1.165:27019")
rs.status()
```
## `NOTE: REMOVE NODE FROM CLUSTET - rs.remove("192.168.1.236:27018")`

# STEP:4 - Login To Secondary Node

```bash
mongosh mongodb://192.168.1.238:27017

# Type 
rs.slaveOk()
```