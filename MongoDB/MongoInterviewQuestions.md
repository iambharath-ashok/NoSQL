#	MongoDB Interview Questions


##	Explain what is MongoDB?

-	Mongo-DB is a document database which provides high performance, high availability and easy scalability.


##	What is “Namespace” in MongoDB?

-	MongoDB stores BSON (Binary Interchange and Structure Object Notation) objects in the collection
-	The concatenation of the collection name and database name is called a namespace.


##	 What is sharding in MongoDB?

-	The procedure of storing data records across multiple machines is referred as Sharding
-	It is a MongoDB approach to meet the demands of data growth
-	It is the horizontal partition of data in a database or search engine. 
-	Each partition is referred as shard or database shard


##	 How can you see the connection used by Mongos?


-	To see the connection used by Mongos use db_adminCommand (“connPoolStats”);


##	 Explain what is a replica set?

-	A replica set is a group of mongo instances that host the same data set
-	In replica set, one node is primary, and another is secondary
-	From primary to the secondary node all data replicates

##	How replication works in MongoDB?

-	Across multiple servers, the process of synchronizing data is known as replication
-	It provides redundancy and increase data availability with multiple copies of data on different database server.
-	Replication helps in protecting the database from the loss of a single server.


##	Mention what is Objecld composed of?


-	Timestamp
-	Client machine ID
-	Client process ID
-	3 byte incremented counter


##	 Mention what is the command syntax for inserting a document?

-	For inserting a document command syntax is database.collection.insert (document).

##	What is the command syntax that tells you whether you are on the master server or not? And how many master does MongoDB allow?

-	Command syntax Db.isMaster() will tell you whether you are on the master server or not. MongoDB allows only one master server, while couchDB allows multiple masters.


##	 What are alternatives to MongoDB?

-	Cassandra, CouchDB, Redis, Riak, Hbase are a few good alternatives.

##	 Mention what is the basic syntax to use index in MongoDB?

-	The basic syntax to use in MongoDB is >db.COLLECTION_NAME.ensureIndex ( {KEY:1} ). 
-	Here the key is the the name of the COLUMN (or KEY:VALUE pair) which is present in the documents.




























