#	MongoDB Sharding


##	What is Sharding in MongoDB?

-	Sharding is a concept in MongoDB, which splits large data sets into small data sets across multiple MongoDB instances
-	Sometimes the data within MongoDB will be so huge, that queries against such big data sets can cause a lot of CPU utilization on the server. 
-	To tackle this situation, MongoDB has a concept of Sharding, which is basically the splitting of data sets across multiple MongoDB instances
-	The collection which could be large in size is actually split across multiple collections or Shards as they are called. 
-	Logically all the shards work as one collection. 



##	How to Implement Sharding

-	Shards are implemented by using clusters which are nothing but a group of MongoDB instances.
-	The components of a Shard include:

	-	A Shard – This is the basic thing, and this is nothing but a MongoDB instance which holds the subset of the data. In production environments, all shards need to be part of replica sets.
	-	Config server – This is a mongodb instance which holds metadata about the cluster, basically information about the various mongodb instances which will hold the shard data.
	-	A Router – This is a mongodb instance which basically is responsible to re-directing the commands send by the client to the right servers.

##	Step by Step Sharding Cluster Example

-	Step 1) Create a separate database for the config server.


		mkdir /datab/configdb
		
-	Step 2) Start the mongodb instance in configuration mode. Suppose if we have a server named Server D which would be our configuration server, we would need to run the below command to configure the server as a configuration server.

		mongod –configdb ServerD: 27019

-	Step 3) Start the mongos instance by specifying the configuration server

		mongos –configdb ServerD: 27019

-	Step 4) From the mongo shell connect to the mongo's instance

		mongo –host ServerD –port 27017

-	Step 5) If you have Server A and Server B which needs to be added to the cluster, issue the below commands

		sh.addShard("ServerA:27017")
		sh.addShard("ServerB:27017")
		
-	Step 6) Enable sharding for the database. So if we need to shard the Employeedb database, issue the below command

		sh.enableSharding(Employeedb)

-	Step 7) Enable sharding for the collection. So if we need to shard the Employee collection, issue the below command

		Sh.shardCollection("db.Employee" , { "Employeeid" : 1 , "EmployeeName" : 1})

-----------------------------------------------------------------------

# MongoDB Replica Set  

##	What is MongoDB Replication?

-	Replication is referred to the process of ensuring that the same data is available on more than one Mongo DB Server. This is sometimes required for the purpose of increasing data availability.

-	Because if your main MongoDB Server goes down for any reason, there will be no access to the data. But if you had the data replicated to another server at regular intervals, you will be able to access the data from another server even if the primary server fails.

-	Another purpose of replication is the possibility of load balancing. If there are many users connecting to the system, instead of having everyone connect to one system, users can be connected to multiple servers so that there is an equal distribution of the load.


##	What is MongoDB Replication?

-	In MongoDB, multiple MongDB Servers are grouped in sets called Replica sets. The Replica set will have a primary server which will accept all the write operation from clients. All other instances added to the set after this will be called the secondary instances which can be used primarily for all read operations.

































