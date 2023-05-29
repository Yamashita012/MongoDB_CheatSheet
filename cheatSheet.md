#MongoDB cheatsheet 

**Connecting to MongoDB**:
```bash
mongo
```

**Switching to a Database**:
```bash
use database_name
```

**Creating a Collection**:
```javascript
db.createCollection("collection_name")
```

**Inserting Documents**:
```javascript
db.collection_name.insertOne({key1: value1, key2: value2, ...})
db.collection_name.insertMany([{key1: value1, key2: value2, ...}, {key1: value1, key2: value2, ...}])
```

**Querying Documents**:
```javascript
db.collection_name.find()
db.collection_name.find({key: value})
db.collection_name.find({key: {$gt: value}})
```

**Updating Documents**:
```javascript
db.collection_name.updateOne({key: value}, {$set: {key1: value1}})
db.collection_name.updateMany({key: value}, {$set: {key1: value1}})
```

**Deleting Documents**:
```javascript
db.collection_name.deleteOne({key: value})
db.collection_name.deleteMany({key: value})
```

**Filtering Documents** (using $filter operator):
```javascript
db.collection_name.aggregate([
  {
    $match: { key: value }
  },
  {
    $project: {
      filteredArray: {
        $filter: {
          input: "$array_field",
          as: "item",
          cond: { $gt: ["$$item", 5] }
        }
      }
    }
  }
])
```

**Sorting Documents** (using sort() method):
```javascript
db.collection_name.find().sort({key: 1}) // Ascending
db.collection_name.find().sort({key: -1}) // Descending
```

**Limiting Documents** (using limit() method):
```javascript
db.collection_name.find().limit(number_of_documents)
```

**Aggregating Data** (using aggregate() method):
```javascript
db.collection_name.aggregate([
  { $group: { _id: "$key", count: { $sum: 1 } } },
  { $sort: { count: -1 } }
])
```

**Indexing** (creating an index):
```javascript
db.collection_name.createIndex({key: 1})
```

**Dropping a Collection**:
```javascript
db.collection_name.drop()
```

**Dropping a Database**:
```javascript
db.dropDatabase()
```

**Working with Date and Time**:
```javascript
// Current Date and Time
var currentDate = new Date()

// Date Comparison
db.collection_name.find({date_field: {$gt: currentDate}})
```

**Aggregation Pipeline**:
```javascript
db.collection_name.aggregate([
  { $match: { key: value } },
  { $group: { _id: "$key", count: { $sum: 1 } } },
  { $sort: { count: -1 } },
  { $limit: 10 }
])
```

**Exporting and Importing Data**:
```bash
# Export a collection to a JSON file
mongoexport --db database_name --collection collection_name --out output.json

# Import data from a JSON file to a collection
mongoimport --db database_name --collection collection_name --file input.json
```

Commonly used commands and operations in MongoDB. 
