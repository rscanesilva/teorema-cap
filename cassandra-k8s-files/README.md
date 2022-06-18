## To install Cassandra, run the following command
    $ kubectl create ns cassandra
    $ kubectl apply -n cassandra -f .

## Configure the port-forward 
    $ kubectl port forward cassandra-0 9042:9042 --namespace="cassandra"

## Install cqlsh localy
    $ pip install cqlsh

## Access the Cassandra's DB pod with CQLSH
    $ cqlsh 127.0.0.1 9042

## Create keyspace
    $ CREATE KEYSPACE firstkeyspace WITH REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : 3 };

## Use keyspace command
    $ USE firstkeyspace

## Create table command
    $ CREATE TABLE firstkeyspace.animal ( id UUID PRIMARY KEY, name text, breed text );

## Insert value command
    $ INSERT INTO firstkeyspace.animal (id, name, breed) VALUES (6ab09bec-e68e-48d9-a5f8-97e6fb4c9b47, 'Bravo','Rottweiler');

## Select command
    $ SELECT * FROM firstkeyspace.animal
