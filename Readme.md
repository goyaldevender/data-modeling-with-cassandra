# About Apache Cassandra
Its was developed by facebook and is inspired from Amazon Dynamo and Google Bigtable.
It is very important to understand partition key and clustering key for data modelling in cassandra.

## What is keyspace in Apache Cassandra
Tables and other items in one keyspace are not visible to other keyspace.
We we can see that we have created a logical partition, using keyspace.

## Primary key: 
First element of our Primary key is called partition key. Its used to determine data
locality. Primary key in cassandra controls the uniqueness and order.

## Partition Key: 
Partition key hashed to determine which nodes or replicas will get the data.
Its option to put parenthesis around single partition key but if we have multiple partition key 
then we need to put parenthesis around it.

## Clustering key 
In a composite Primary key, all the columns after the partition key are called clustering columns.
Clustering column specifies the order that the data is arranged inside the partition.
Example: PRIMARY KEY((city, state)). Here state is cluster column.
If we have multiple cluster column, then we are essentially saying first order by c1 then order by c2.
Its helps in greater than, equal than, less than queries. It will take advantage of binary search.

#### Usage: 
The default clustering order is ascending. But we can change the order by adding
"`WITH CLUSTERING ORDER BY`" clause.
        

## Pulling the cassandra image from internet
`docker pull cassandra`

## Starting the cassandra container
`docker run --name cassandra-container -p 9042:9042 -d cassandra:latest`


## Installing cassandra driver
In case, you are not able to install `cassandra` then you can install
`cassandra-driver`, and it should work fine.
`pip3 install cassandra-driver`