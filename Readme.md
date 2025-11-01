# MongoDB

## Installation

-"<https://www.mongodb.com/try/download/community>"
-"<https://www.mongodb.com/try/download/shell>"
-"<https://www.mongodb.com/try/download/database-tools>"

## Introduction

- MongoDB is a document-oriented database
- MongoDB is a schema-less database
- MongoDB is a cross-platform database
- MongoDB is a NoSQL database

### Data Model

 Data stored in form of tables called collections
    - Each collection contains multiple documents
    - Each document is a set of key-value pairs
    - Each document is unique
    - Documents can have different fields
    - Documents can be nested
    - Documents can be indexed
    - Documents can be queried using a query language
    - Documents can be updated
    - Documents can be deleted
    - Documents can be aggregated
    - Documents can be replicated
    - MongoDB is a horizontally scalable database

## DataFlow

- Node > MongoDB > Collections > Documents

## JSON vs BSON

- In MongoDB we write in JSON format only but behind the scene it converts to BSON (Binary JSON) format.
- BSON is a binary representation of JSON-like documents.
- BSON is used to achieve higher read and write speeds, improved data manipulation, and better integration with other MongoDB tools.

## Commands

### Basic Commands

- `show dbs` - Show all databases
- `use <database>` - Use a database
- `show collections` - Show all collections
- `db.<collection>.find()` - Find all documents in a collection
- `db.<collection>.insertOne({})` - Insert a document into a collection
- `db.<collection>.updateOne({}, {})` - Update a document in a collection
- `db.<collection>.deleteOne({})` - Delete a document from a collection

### Note

- If there is no collections in a db then it won't show any collections.

### Inserting Documents

- `db.<collection>.insertOne({'name': 'John Doe', 'age': 30})` - Insert a document into a collection
- `db.<collection>.insertMany([{'name': 'Jane Doe', 'age': 25}, {'name': 'Jim Doe', 'age': 35}])` - Insert multiple documents into a collection
- `db.<collection>.insertMany([{'name': 'Jake Doe', 'age': 40}, {'name': 'Jill Doe', 'age': 45}])` - Insert multiple documents into a collection

### Inserts types

- ordered - Insert documents in the order they are provided
- if there is any duplicate key then it will throw an error and stop the insertion, if there is any valid document before the error then it will insert that document.
- unordered - Insert documents in any order
-syntax: `db.<collection>.insertMany([{}, {}], {ordered: false})`

### show Commands

- `db.<collection>.find()` - Find all documents in a collection
- `db.<collection>.find({})` - Find documents in a collection based on a query
- `db.<collection>.find({}).limit(10)` - Find documents in a collection based on a query and limit the result to 10 documents
- `db.<collection>.find({}).sort({})` - Find documents in a collection based on a query and sort the result
- `db.<collection>.find({}).count()` - Find documents in a collection based on a query and count the result

## Delete Commands

- `db.<collection>.deleteOne({})` - Delete a document from a collection
- `db.<collection>.deleteMany({})` - Delete multiple documents from a collection
- `db.<collection>.drop()` - Drop a collection
- `db.dropDatabase()` - Drop the current database

## Importing JSON Data

- `mongoimport jsonfile.json -d <database> -c <collection>` - Import JSON data into a collection (if there is objects only)
- `mongoimport jsonfile.json -d <database> -c <collection> --jsonArray` - Import JSON data into a collection (if there is array of objects)

## Logical Operators

- `$and` - Returns documents that match all the specified conditions
- `$or` - Returns documents that match any of the specified conditions
- `$not` - Returns documents that do not match the specified condition
- `$nor` - Returns documents that do not match any of the specified conditions
-syntax: `db.<collection>.find({$and: [{}, {}]})`
-syntax: `db.<collection>.find({$or: [{}, {}]})`
-syntax: `db.<collection>.find({$not: {}})`
-syntax: `db.<collection>.find({$nor: [{}, {}]})`
