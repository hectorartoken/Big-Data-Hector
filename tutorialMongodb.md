# MongoDB
## How to install it?
1. Open the link [MongoDB](https://www.mongodb.com/es)
2. Click in **software**, then **community server**.
3. You need to insatll MongoDB Community Server.
4. On *OS*, you must select your operating system.
5. On *Version*, It's recommendable select the version that says **(current realse)**.
6. On *Package* select "MSI".
7. Click **Download**
8. If you want more information about how to intall it, whatch this video [DowlandMongoDB](https://www.youtube.com/watch?v=gkCnXcxHC4o)

## What is MongoDB?
It is an open source non-SQL database. I was able to handle large amounts of data quickly.

## Getting start
We can access MongoDB throug the terminal application.
How to open the Mongo Shell?:
* First open the file **Archivos de programa**, then **MongoDB**, then **Server**, then **4.2**(according to your version), then **bin**, 
finally you must first execute the program **mongod.exe** and then **mongo.exe**. Now you are in Mongo Shell.
* If you have te extension, you can execute MongoDB with the command `mongo`.

## How do we interact with MongoDB?
All instances of MongoDB come with a command line program we can use to interact with our database using JavaScript.
```javascript
> var potion = {
	"name": "posion",
	"vendor": "witch01"
}
> potion
{
	"name": "posion",
	"vendor": "witch01"
}
```

## Using the Shell 
MongoDB comes with helper methods to make it easy to interact with the database.
```javascript
> help // Show list of commands
db.help() ...
...
show dbs ...

> show dbs // Show list of databases
test 0.078GB
reviews 0.078GB

> use reviews // Switches to use the database and creates it if doesn't exist when we write to it
switched to db reviews

> db // Returns the current database name
reviews
```

## Documents need to be stored in collections
documents are always stored in collections within a database.
```javascript
// Potion Document
{
	"name": "posion",
	"vendor": "witch01"
}
// Document must be placed in a collection
```

## Inserting a document into a collection 
we can use the `insert()` collection method to save a potion document to the potions collection.
```javascript
// The collection that you will create doesn´t exit yet, so it will automatically be created
// In this example I'll create a collection *hector*, but you can choose another name.
// To write to the database, we specify the collection and the operation to perform
> db.hector.insert( // hector document as a parameter of the insert method
{
	"name" : "posion",
	"vendor" : "
}
)

WriteResult({ "nInserted": 1})
```

## What's a WriteResult?
Whenever we write to the database, we'll always be returned a WriteResult object that tells us if the operation was successful or not.

```javascript
> db.hector.insert(
{
	"name": "posion",
	"vendor": "witch01"
}
)
WriteResult({ "nInserted": 1})
```

## Finding all potions
we can use the `find()` collection method to retrieve the potion from the inventory collection.
```javascript
> db.hector.find() // All collection methods must en with parentheses
{
	"_id" : ObjectId("5eb590f567f26bd27a22d1a2"), // unique id that gets automatically generated
	"name" : "posion",
	"vendor" : "witch01"
}
```

## Using find to return all documents in a collection
```javascript
> db.hector.insert(...) // Let's add 2 more potions
WriteResult({ "nInserted": 1})

> db.hector.insert(...)
WriteResult({ "nInserted": 1})

> db.hector.find() // now find returns a total of 3 potions
{ "name": "posion" ...},
{ "name": "fire resistance" ...},
{ "name": "invisibility" ...}
```




















