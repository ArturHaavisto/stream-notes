- **Decentralized Generation:** Drivers (like the one Mongoose uses) can generate the `ObjectId` on the client side, even before communicating with the database, which speeds up insertions.
- `ref` is what makes Mongoose smart about relationships, allowing it to "join" data from separate collections using the `populate()` method
# Basic
```
get into the terminal: mongosh
	exit: exit
show dbs
show collections
db.dropDatabase()
Create db: use <db name>
Create collection: db.createCollection("<name>")
- "<name>", {capped:true, size:10000000, max:100}, {autoIndexId:false/true}
Insert: db.<collection-name>.insertOne({key:value})
Insert many: db.<collection-name>.insertMany([{key:value}, {key:value}])
```
# Query
```
Find: db.<collection-name>.find()
Sort: db.<collection-name>.find().sort({key:1}) (1=asc, -1=desc)
Limit: db.<collection-name>.find().limit(1)
Find advanced: db.<collection-name>.find({query}, {_id:false, <key>:true})
```


# Update and remove
```
Update: db.<collection>.updateOne({filter}, {update})
Update add new field: db.<collection-name>.updateOne({key:value}, {$set:{<new-key>:value}})
Update based on id ... UpdateOne({_id: ObjectId("<id>")}, {$set:...})
Remove field ... $unset:{key:""}
Does the field exist: {<key>:{$exists:<true/false>}}
Delete data: db.<collection>.removeOne/Many({filter})
```

# Filter
```
filter, not equal: ... {<key>:{$ne:<value>}}
filter, less than: $lt
filter, less than equal to: $lte
greater than: $gt
more than one filter: {$gte:<value>, $lt:<value>}
in an array: $in: []
not in: $nin
logical: $and, $not, $nor, $or: [{}, {}]
```

# Stats
```
...find().explain("executionStats")
```

# Indexes
```
db.<collection>.createIndex({<key>:1/-1})
db.<collection>.getIndexes()
db.<collection>.dropIndex(<name>)
```
- Indexing is handy for a lot of searching, but not good for updating