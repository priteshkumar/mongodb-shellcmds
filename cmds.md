## mongosh commands for mongodb

> create database : use new_db

> create collection : db.createCollection("temp")

>list collections : show collections

> count records in collection : ```db.temp.countDocuments()```

> list all documents in collection : ```db.temp.find()```

> find one document in collection : ```db.temp.findOne()```

> limit the number of documents : ```db.temp.find().limit(5)``` --> returns 5 documents

> retreive only few fields in documents : ```db.temp.find({},{listing_url:1,name:1,property_type:1,_id:0}).limit(3)``` --> this will select only listing_url,name,property_type fields of documents

> retreive specific subfields in embedded document : ```db.temp.find({property_type:"Apartment"},{host:{host_url:1,host_name:1},_id:0}).limit(5)```

--> this only retreives host_url,host_name subfields 

> ```db.temp.find({property_type:"Apartment"}).count()``` --> counts the number of documents having property_type = "Apartment"

> ```db.temp.find({},{name:1,listing_url:1,minimum_nights:1}).sort({minimum_nights:-1}).limit(10)```  --> sorts in desc order based on minimum_nights

> ```db.temp.updateOne({_id:'10006546'},{$set:{minimum_nights:'4'}})``` --> updates document with id , setting minimum_nights to 4

> ```db.temp.find({minimum_nights:{$ne:'2'}},{listing_url:1,minimum_nights:1}).limit(10)``` --> finds the documents where minimum_nights != 2

> ```db.temp.find({$and:[{beds:{$gte:15}},{beds:{$lte:26}}]},{listing_url:1,name:1,beds:1}).sort({beds:-1})``` ---> finds documents with beds >= 15 and beds <= 26

> ```db.temp.distinct('property_type')``` --> finds the distinct values for property_type field

### Aggregation cmds

> ```db.temp.aggregate([{$group:{_id:"$property_type",numOfproperties:{$sum:1}}}])``` --> finds the num of properties for each property_type
