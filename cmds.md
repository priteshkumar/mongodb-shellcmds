## mongosh commands for mongodb

> create database : use new_db

> create collection : db.createCollection("temp")

>list collections : show collections

> count records in collection : db.temp.countDocuments()

> list all documents in collection : db.temp.find()

> find one document in collection : db.temp.findOne()

> limit the number of documents : db.temp.find().limit(5) --> returns 5 documents 
