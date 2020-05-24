# MongoDB
![alt text](https://github.com/hectorartoken/Big-Data-Hector/blob/master/Images/MongoDB.png "MongoDB")
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
* If you have the extension, you can execute MongoDB with the command `mongo`.

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
Documents are always stored in collections within a database.
```javascript
// Potion Document
{
	"name": "posion",
	"vendor": "witch01"
}
// Document must be placed in a collection
```

## Inserting a document into a collection 
We can use the `insert()` collection method to save a potion document to the potions collection.

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
We can use the `find()` collection method to retrieve the potion from the inventory collection.
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

## Finding a specific potion with a query
We can perform a query of equality by specifying a field to query and the value we'd like.

```javascript
// Queries are feld/values pairs
> db.hector.find({"name": "posion"})
{
	"_id" : ObjectId("5eb590f567f26bd27a22d1a2"), 
	"name" : "posion",
	"vendor" : "witch01"
}
// Queries will return all the felds of matching documents
```

## Queris that return multiple values

```javascript
> db.hector.find({"vendor": "witch01"})
{
	"_id" : ObjectId("5eb590f567f26bd27a22d1a2"),
	"name" : "posion",
	"vendor" : "witch01"
}
{
	"_id" : ObjectId("5eb5971d67f26bd27a22d1a4"),
	"name" : "invisibility",
	"vendor" : "witch01"
}
```

## What else can we store?
Documents are persisted in a format called BSON

BSON is liek JSON, so you can store:

String: `"posion"`

Numbers: `1400` `2.17`

Booleans: `true` `false`

Arrays: `["redstone", "water"]`

Objects: `{"type": "bottle"}`

Null : `null`

BSON cmes with some extras

ObjectID: `ObjectId(...)`

Date: `ISODate(...)`

## Adding Power and Level
We can store both integers and floats in a document.

```javascript
{
	"name": "posion",
	"vendor": "witch01",
	"power" : 11.5,
	"level" : 2 
}
```

## Adding a CreateDate
Dates can be added using the JavaScript Date object and gent saved in the database as an ISODate object.

```javascript
{
	"name": "posion",
	"vendor": "witch01",
	"power" : 11.5,
	"level" : 2,
	"createDate" : new Date(2020, 4, 13) // Reads as May 13, 2012, since JavaScript months begin at 0
}

"createDate" : ISODate("2020-05-13T05:00:00Z")
```

## Adding a List of Ingredients
Arrays are great option for storing lists of data.

```javascript
{
	"name": "posion",
	"vendor": "witch01",
	"power" : 11.5,
	"level" : 2,
	"createDate" : new Date(2020, 4, 13),
	"ingredients" : ["redstone", "eyespider", 12]
}
```

## Embedded Documents
We embed documents simply by adding the document as a value for a given field.

```javascript
{
	"name": "posion",
	"vendor": "witch01",
	"power" : 11.5,
	"level" : 2,
	"createDate" : new Date(2020, 4, 13),
	"ingredients" : ["redstone", "eyespider", 12],
	"statistics" : {"damage": 5, "type": "bottle"}
}
```

## Inserting Our New Potion

```javascript
> db.hector.insert({
	"name": "posion",
	"vendor": "witch01",
	"power" : 11.5,
	"level" : 2,
	"createDate" : new Date(2020, 4, 13),
	"ingredients" : ["redstone", "eyespider", 12],
	"statistics" : {"damage": 5, "type": "bottle"}
})

WriteResult({ "nInserted": 1 })
```
Now you must add in your other documents that format with the same keys but different values.

```javascript
> db.hector.insert({
{
        "name" : "instantDamage",
        "vendor" : "witch01",
        "power" : 13.5,
        "level" : 2,
        "createDate" : new Date(2020, 4, 13),
        "ingredients" : ["netherWart","fermentedSpiderEye",13],
        "statistics" : {"damage" : 8,"type" : "splash"}
}
{
        "name" : "weakness",
        "vendor" : "witch02",
        "power" : 8.5,
        "level" : 1,
        "createDate" : new Date(2020, 4, 13),
        "ingredients" : ["gunpowder","fermentedSpiderEye",5],
        "statistics" : {"damage" : 3,"type" : "splash"}
}
{
        "name" : "force",
        "vendor" : "witch02",
        "power" : 14.5,
        "level" : 1,
        "createDate" : new Date(2020, 4, 13),
        "ingredients" : ["netherWart","blazepowder",8],
        "statistics" : {"damage" : 0,"type" : "bottle"}
}
{
        "name" : "regeneration",
        "vendor" : "witch03",
        "power" : 6,
        "level" : 2,
        "createDate" : new Date(2020, 4, 13),
        "ingredients" : ["netherWart","ghastTear",3],
        "statistics" : {"damage" : 0,"type" : "bottle"}
}
})

WriteResult({ "nInserted": 4 })
```

## Finding Potions by ...

### Array
Array values are treated individually, wich means we can query them by specifying the field
of the array and the value we'd like to find.

```javascript
> db.hector.find({"ingredients": "gunpowder"}).pretty() // We can use the function .pretty() to show the query as:
{
        "_id" : ObjectId("5eca0a1dd28e00ab8306d72f"),
        "name" : "weakness",
        "vendor" : "witch02",
        "power" : 8.5,
        "level" : 1,
        "createDate" : ISODate("2020-05-13T05:00:00Z"),
        "ingredients" : [
                "gunpowder",
                "fermentedSpiderEye",
                5
        ],
        "statistics" : {
                "damage" : 3,
                "type" : "splash"
        }
}
// we can note that into ingrdients there is the ingredient "gunpowder"
```
### Embedded
We can search for potions by their ratings using dot natation to specify the embedded field
we'd like to search

```javascript
> db.hector.find({"statistics.damage": 3})
{
        "_id" : ObjectId("5eca0a1dd28e00ab8306d72f"),
        "name" : "weakness",
        "vendor" : "witch02",
        "power" : 8.5,
        "level" : 1,
        "createDate" : ISODate("2020-05-13T05:00:00Z"),
        "ingredients" : [
                "gunpowder",
                "fermentedSpiderEye",
                5
        ],
        "statistics" : {
                "damage" : 3,
                "type" : "splash"
        }
}
```

## Delete a Single Document
The `remove()` collection method will delete documents that match the provided query.

```javascript
> db.hector.remove({"name":"posion"})
WriteResult({ "nRemoved": 1})
```

## Delete Multiple Documents
If our query matches multiple documents, the `remove()` will delete all of them.

```javascript
> db.hector.remove({"vendor":"witch01"})
WriteResult({ "nRemoved": 2})
```

## Upsating a Document
We can use the `upadate()` collection method to modify existing documents

```javascript
> db.hector.update(
	{"name":"posion"}, // Query parameter
	{"$set": {"power" : 7.3}} // Update parameter. Update operators always begin with a $
)
WriteResult({              
	"nMatched": 1, // Number of documents matched      
	"nUpserted": 0, // Number of documents that were ceated
	"nModified": 1 // Number of documents modified
	})


```
## Updating Multiple Documents
The update method can take a third parameter for options.

```javascript
> db.hector.update(
	{"vendor": "witch02"},
	{"$set": {"vendor": "witchNumberp02"}},
	{"multi": true} // When multi is true, the update modifies all matching documents	
)
WriteResult({              
	"nMatched": 2,      
	"nUpserted": 0,      
	"nModified": 2 
})
```

## Find or Create With Upsert
The upsert option either updates an existing document or creates a new one

```javascript
> db.hector.update(
	{"name": "posion"},
	{"$inc" : {"count":1}}, // If the field doesn't exist, it gets created with the value
	{"upsert": true} // creates a document using the values from the query and update parameter
)
WriteResult({
        "nMatched" : 0,
        "nUpserted" : 1, // 1 document created
        "nModified" : 0,
        "_id" : ObjectId("5eca3f6f7148427c1d64ebec")
})
```

## Updating Once More
If we run the same update again, the update will act normally and `upsert` won't create another document.

```javascript
> db.hector.update(
	{"name": "posion"},
	{"$inc":{"count": 1}},
	{"upsert": true})
)
WriteResult({               
	"nMatched": 1,  // Document found and modified but nothing created     
	"nUpserted": 0,       	
	"nModified": 1
	})

> db.hector.find({"name":"posion"}).pretty()
{
        "_id" : ObjectId("5eca04b9d389c053a9337807"),
        "name" : "posion",
        "vendor" : "witch01",
        "power" : 11.5,
        "level" : 2,
        "createDate" : ISODate("2020-05-13T05:00:00Z"),
        "ingredients" : [
                "redstone",
                "eyespider",
                12
        ],
        "statistics" : {
                "damage" : 5,
                "type" : "bottle"
        },
        "count" : 2
}
```

## Removing Fields From Documents
We initially thought we'd need a potion's level, but we never use it. The `$unset` operator can 
be used to remove specified fields.

```javascript
> db.hector.update(
	{}, // Uery for all potions
	{"$unset": {"level": ""}}, // The value we pass doesn't impact the operation
	{"multi":true} // Update all potions
)
WriteResult({ "nMatched" : 5, "nUpserted" : 0, "nModified" : 5 })
```

We can use `$rename` to change filed names.

```javascript
> db.hector.update( 
	{},
	{"$rename": {"power": "damage"}},      
	{"multi": true}
)
WriteResult({ "nMatched" : 5, "nUpserted" : 0, "nModified" : 5 })

> db.hector.find()
{ "_id" : ObjectId("5eca04b9d389c053a9337807"), "name" : "posion", "vendor" : "witch01", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "redstone", "eyespider", 12 ], 
"statistics" : { "damage" : 5, "type" : "bottle" }, "count" : 2, "damage" : 11.5 }
{ "_id" : ObjectId("5eca09a1d28e00ab8306d72e"), "name" : "instantDamage", "vendor" : "witch01", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "netherWart", "fermentedSpiderEye", 13 ], 
"statistics" : { "damage" : 8, "type" : "splash" }, "damage" : 13.5 }
{ "_id" : ObjectId("5eca0a1dd28e00ab8306d72f"), "name" : "weakness", "vendor" : "witch02", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "gunpowder", "fermentedSpiderEye", 5 ], 
"statistics" : { "damage" : 3, "type" : "splash" }, "damage" : 8.5 }
{ "_id" : ObjectId("5eca0a9ed28e00ab8306d730"), "name" : "force", "vendor" : "witch02", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "netherWart", "blazepowder", 8 ], 
"statistics" : { "damage" : 0, "type" : "bottle" }, "damage" : 14.5 }
{ "_id" : ObjectId("5eca0ad7d28e00ab8306d731"), "name" : "regeneration", "vendor" : "witch03", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "netherWart", "ghastTear", 3 ], 
"statistics" : { "damage" : 0, "type" : "bottle" }, "damage" : 6 }
```

## Updating Single Array Value
The `$set` operator will update the value of a specified field

```javascript
> db.hector.update(
	{"name": "posion"},
	{"$set" : {"ingredients.2": 23}} 
    // We need type the position of the value into the array that we want to change
	// the value is the postion 3, so we need type .2 because into array we start to count from 0  
)
WriteResult({"nMatched": 1,"nUpserted": 0,"nModified: 1})

// change succesful
> db.hector.find({"name":"posion"})
{ "_id" : ObjectId("5eca04b9d389c053a9337807"), "name" : "posion", "vendor" : "witch01", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "redstone", "eyespider", 23 ], 
"statistics" : { "damage" : 5, "type" : "bottle" }, "count" : 2, "damage" : 11.5 }
```

## Updating Values Without Knowing position
The postional operator is a placeholder that will set the proper position for the value 
specified in the query parameter.

```javascript
> db.hector.update(
	{"ingredients" : "netherWart"}, // Query for the value we want to change
	{"$set": {"ingredients.$" : "water"}}, // The $ is a placeholder for the matched value
	{"multi": true} // Multi is true to make the change to all documents
)
WriteResult({ "nMatched" : 3, "nUpserted" : 0, "nModified" : 3 })

//Only updates the first match per document
```

## Updating an Embedded Value
We can update using the dot notation to specify the field we want to update

```javascript
> db.hector.update(
	{"name":"instantDamage"},
	{"$set" : {"statistics.damage" : 10}}
)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
```

## Useful Update Operators
MongoDB provides a variety of ways to modify the values of fields.

`$max` Update if new value is greater than current or inserts if empty

`$min` Updates if new value is less than current or insert if empty

`$mul` Multiplies current field value by specified value. if empty, it insert 0.

## Removing the First or Last Value of an Array
The `$pop` operator will remove either the first or last value of an array

```javascript
> db.hector.update(
	{"name": "weakness"},
	{"$pop": {"ingredients" : 1}}
	// -1 removes the first element
	// 1 removes the last element	
)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

// Doesn't return the value, only modifies the array
> db.hector.find({"name":"weakness"})
{ "_id" : ObjectId("5eca0a1dd28e00ab8306d72f"), "name" : "weakness", "vendor" : "witch02", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "gunpowder", "fermentedSpiderEye" ], 
"statistics" : { "damage" : 3, "type" : "splash" }, "damage" : 8.5 }
```

## Adding Values to the End of an Array

```javascript
> db.hector.update(
	{"name" : "weakness"},
	{"$push" : {"ingredients": 14}}
)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.hector.find({"name":"weakness"})
{ "_id" : ObjectId("5eca0a1dd28e00ab8306d72f"), "name" : "weakness", "vendor" : "witch02", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "gunpowder", "fermentedSpiderEye", 14 ], 
"statistics" : { "damage" : 3, "type" : "splash" }, "damage" : 8.5 }
```

## Adding Unique Values to an Array
The `$addToSet` operator will add a value to the end of an array unless it is already present.

```javascript
> db.hector.update(
	{"name" : "force"},
	{"$addToSet": {"ingredients": "netherWart"}}
)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.hector.find({"name":"force"})
{ "_id" : ObjectId("5eca0a9ed28e00ab8306d730"), "name" : "force", "vendor" : "witch02", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "water", "blazepowder", 8, "netherWart" ], 
"statistics" : { "damage" : 0, "type" : "bottle" }, "damage" : 14.5 }
```

## Removing Values From an Array
The `$pull` operator will remove any instance of a value from an array

```javascript
> db.hector.update(
	{"name":"force"},
	{"$pull" : {"ingredients" : "water"}}
)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.hector.find({"name" : "force"})
{ "_id" : ObjectId("5eca0a9ed28e00ab8306d730"), "name" : "force", "vendor" : "witch02", 
"createDate" : ISODate("2020-05-13T05:00:00Z"), "ingredients" : [ "blazepowder", 8, "netherWart" ], 
"statistics" : { "damage" : 0, "type" : "bottle" }, "damage" : 14.5 }
```













































