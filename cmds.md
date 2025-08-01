## mongosh commands for mongodb

> create database : use new_db

> create collection : db.createCollection("temp")

>list collections : show collections

> count records in collection : db.temp.countDocuments()

> list all documents in collection : db.temp.find()

> find one document in collection : db.temp.findOne()

> limit the number of documents : db.temp.find().limit(5) --> returns 5 documents

> retreive only few fields in documents : db.temp.find({},{listing_url:1,name:1,property_type:1,_id:0}).limit(3) --> this will select only listing_url,name,property_type fields of documents

> retreive specific subfields in embedded document : db.temp.find({property_type:"Apartment"},{host:{host_url:1,host_name:1},_id:0}).limit(5)

--> this only retreives host_url,host_name subfields  
