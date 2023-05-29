# MongoDB_CheatSheet
This is a MongoDB cheatsheet mainly for beginners.

**Key points about collections in MongoDB:**

1.  *Schema-less Structure:* - Unlike traditional relational databases, MongoDB is schema-less, which means that documents within a collection can have different structures or fields. Each document within a collection is independent and can have its own unique fields.

2.  *Document Storage:* - MongoDB stores data in BSON (Binary JSON) format, which is a binary representation of JSON-like documents. These documents are flexible and can have nested structures, arrays, and various data types.

3.  *No Predefined Structure:* - Collections do not require a predefined structure or schema. You can insert documents into a collection without explicitly defining its fields or data types. This flexibility allows for easy evolution of data models.

4.  *Dynamic Schema:* - MongoDB allows adding or modifying fields within a document without impacting other documents in the collection. This feature is particularly useful when dealing with evolving data models or rapidly changing requirements.

5.  *Document Indexing:* - Collections support indexing, which improves query performance by creating indexes on specific fields. Indexes allow for faster data retrieval, sorting, and filtering.

6.  *Atomic Operations:* - MongoDB provides atomicity at the document level, ensuring that each write operation is atomic within a single document. This means that updates to a single document are either fully applied or not applied at all.

7.  *Scalability:* - Collections can scale horizontally across multiple servers or instances, providing the ability to handle large amounts of data by distributing it across different shards or nodes.

### To interact with a collection in MongoDB, you can use various operations such as inserting documents, querying data, updating documents, deleting documents, and performing aggregations. These operations allow you to manipulate and retrieve data from collections based on your application requirements.
