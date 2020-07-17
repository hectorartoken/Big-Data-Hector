# CHAPTER 1
## Reliable, Scalable, and Maintainable Applications

1. What is Data System (within the Context of Education), with examples?

A computerized system that houses and displays student, educator, and school information and allows users to retrieve, manage, and analyze the data. 
Examples of data systems include an assessment system, data mart, data warehouse, decision support system (DSS), instructional management system (IMS), 
learning management system (LMS) and more.

2. What are the three concerns that are important in most software systems?

Realiability, Scalability and Maintainability

3. What is the different between *fault* and *failure*? 

A fault is usually defined as one component of the system deviating from its spec, 
whereas a failure is when the system as a whole stops providing the required service to the user.

4. Metion two examples of systematic error within the system:

* A software bug that causes every instance of an application server to crash when given a particular bad input. 
* A runaway process that uses up some shared resource—CPU time, memory, disk space, or network bandwidth.

5. How to make the systems reliable, in spite of unreliable humans?

* Design systems in a way that minimizes opportunities for error.
* Decouple the places where people make the most mistakes from the places where
they can cause failures. 
* Test thoroughly at all levels, from unit tests to whole-system integration tests and
manual tests
* Allow quick and easy recovery from human errors, to minimize the impact in the
case of a failure.
* Set up detailed and clear monitoring, such as performance metrics and error
rates. In other engineering disciplines this is referred to as telemetry.

6.Why is it important to check our program for bugs?  How harmful can a bug be?  

Because a bug is a flaw in the software. And a bug can cause tremendous economic losses to companies or even loss of life.

7. What is the different between *latency* and *reponse time*?

The response time is what the client sees: besides the actual time to process the request (the service time), it includes
network delays and queueing delays. Latency is the duration that a request is waiting to be handled—during which it is latent, awaiting service

# CHAPTER 2
## Data Models and Query Languages

1. What do Object-relational mapping (ORM) frameworks do?

Eeduce the amount of boilerplate code required for this translation layer (OOP -> SQL), but they can’t completely hide the differences between the two models.

2. How do we express hierarchy in document models?

Document databases reverted back to the hierarchical model in one aspect: storing nested records (one-to-many relationships, like positions, 
education, and contact_info) within their parent record rather than in a separate table.

Relational and document databases are not fundamentally different: in both cases, the related item is referenced by a unique identifier, 
which is called a foreign key in the relational model and a document reference in the document model.

3. Describe each of the proposed solutions for the limitation of the hierarchical model.

* **Network model**: A record could have multiple parents. The links between records in the network model were not foreign keys, but more like 
pointers in a programming language The only way of accessing a record was to follow a path from a root record along these chains of links. 
This was called an access path.

* **Relational model**: A relation (table) is simply a collection of tuples (rows). The query optimizer automatically decides which parts of the 
query to execute in which order, and which indexes to use.

4. What are Triple-Stores?

In a triple-store, all information is stored in the form of very simple three-part statements: subject, predicate, object.

5. What was the original purpose of Relational Databases?

Their roots lie in dusiness data processing in the 1960s and '70s, mainly used for transaction processing and batch processing.

6. What is database normalization?

It is the process of structure a relational database in a serio of normal forms. The latter with the purpose od reducing data redundancy and to 
improve its data integrity.

7. What is the problem of no having schema?

Means that arbitrary keys and values can be added to a document, and when reading clients have no guarentees as to what fields the documents may contain.

8. When is recommended to use the IMS (Hierarchical Model)?

It works well for one-to-many relationship.

9. What is Polyglot Persistence?

Refers to using different data storage technologies to handle varying data storage needs. It’s an offshoot of polyglot programming, 
which means using different programming languages to build an application.

10. What is cypher?

Cypher is a declarative query language for property graphs, created for the Neo4j graph database.

# CHAPTER 3
## Storage and Retrieval

1. What meaning does the book use for *log*?

The book used is as an append-only sequence of records

2. We have the next functio for a database:
``` bash
db_get(){
	grep "^$1," database | sed -e "s/^$1,//" | tail -n 1
}
```

What is the problem of that function?

The function has a terrible performance if you have a large number of records in your database.

3. Taking the above function, What is its running-time?

O(n).

4. What is a Bloom Filter and its is benefy?

It's a a memory-efficient data structure for approximating the contents of a set. It can tell you if a key does 
not appear in the database, and thus saves many unnecessary disk reads for non-existent keys.

5. Acoording to the book, what is compaction?

Compactions means throwing away duplicate keys in the log, and keeping only the most recent update for each key.

6. Why is common used the Heap File?

Because because it avoids duplicating data when multiple secondary indexes are present: each index just references 
a location in the heap file, and the actual data is kept in one place.

# CHAPTER 4

## Enconding and Evolution

1. What are the directions to keep a system running with old and new code? 

* **Backward compatibility**: Newer code can read data that was written by older code.

* **Forward compatibility**: Older code can read data that was written by newer code.

2. What manipulates and optimizes for efficiency the following data structure: objects, structs, lists, arrays, hash tables, trees, etc?

The CPU

3. What is the meaning of *serialization* in the context of transactions?

Serializability of transaction refers the sequence of actions such as read, write, abort, commit are performed in such a way that it seems 
like the transaction are performed in some serial manner.

4. Mention some problems that have the encoding libraries...

* Reading the data in another language is very difficult.

* The store or transmit data in an encoding.

* Restore data in the same object types.

* They have probelms with the efficiency.

5. What are the standardized encodings that can be written and read by many programming languages?

* JSON

* XML

6. What is the **Binary encoding**?

Binary encoding uses the binary digit, or bit, as the fundamental unit of information, and a bit may only be a ‘0’ or a ‘1’ 
(only two possibilities since it is a binary-encoded system).

7. How this binary serialization deals with APIs?
These APIs are naturally verbose and do not match very well against common language patterns, becuase they are machine-written and not human-written, 
but they work well enough.

8. What are the Thrift and Protocol Buffers?

Apache Thrift and Protocol Buffers are binary encoding libraries that are based on the same principle.  Protocol Buffers was originally developed at Google, 
Thrift was originally developed at Facebook, and both were made open source in 2007–08.

9. How does work the accessing a data base at the same time?

* The writing process: This may be written a newer versions of the code which is being update in the moment of the code running and some will be runing older code.

* The reading process: This is like a batch which reads the older version of the codad that is still running.

10. What is Data Flow?

Data flow is how data flows through your system. It involves thinking about data usage patterns, application boundaries, and similar such things.

# CHAPTER 5

## Replication

1. What is refered as a shared-memory architecture?

Join many CPUs, RAM chips and disks together under one operating system, and a fast interconnect that allows any CPU to access any part of memory or disk.

2. What is the shared-nothing architectures approach?

In this approach, each machine or virtual machine running the database software is called a node. Each node uses uses its CPUs, RAM and disks independently. 
Any coordination between nodes is done at the software level, using a conventional network. No special hardware is required by a shared-nothing system and 
it can potentially distribute data across multiple geographic regions, and thus reduce latency for users and potentially be able to survive the loss of an 
entire datacenter.

3. What does guarantee read-your-writes-consistency?

It guarantee that if the user reload the page, they will always seen any updates they submmited themselves but not promises about the other users.

4. Why is better to used Multi-leader configurations than single-leader?

* Performance: Every write can be processed in the local datacenter and is replicated asynchronously to other datacenters.

* Tolerance of datacenter outages: It allows each datacenter can continue operating idenpendently of the others.

* Tolerance of networks problems: It uses asynchronous replication can usually tolerate newtwork problems.

5. What happens in reality when you implement synchronous replication?

In practice, if you enable synchronous replication on a database, it usually means that one of the followers is synchronous, and the others are asynchronous. 
If the synchronous follower becomes unavailable or slow, one of the asynchronous followers is made synchronous. This configuration is sometimes also 
called semi-synchronous

6. How do we differentiate synchronous replication from the asynchronous?

For example, when replication is synchronous, the leader waits until followers have confirmed that they received the write before reporting success to the user. 
When the leader sends the message, but doesn’t wait for a response from the follower is asynchronous replication.

7. How do you achieve high availability with leader-based replication?

* Follower failure: Catch-up recovery: On its local disk, each follower keeps a log of the data changes it has received from the leader. If a follower crashes 
and is restarted, or if the network between the leader and the follower is temporarily interrupted, the follower can recover quite easily: from its log, 
it knows the last transaction that was processed before the fault occurred.

* Leader failure: Failover, one of the followers needs to be promoted to be the new leader, clients need to be reconfigured to send their writes to the new leader, 
and the other followers need to start consuming data changes from the new leader.

8. What is and in what case would you want to provide cross-device read-after-write consistency?

If the user enters some information on one device and then views it on another device, they should see the information they just entered
When the same user is accessing your service from multiple devices, for example a desktop web browser and a mobile app.

9. What is a sloppy quorum?

In a large cluster (with significantly more than n nodes) it’s likely that the client can connect to some database nodes during the network interruption, 
just not to the nodes that it needs to assemble a quorum for a particular value.

10. What is Trigger-based replication?

To implement trigger-based replication, use event triggers stored in the database. When an event to be replicated occurs 
(that is, a record is created, modified, or deleted) the database uses the event to record the change in a replication change log. ABL (Advanced Business Language) 
provides full support for trigger-based replication.

# CHAPTER 6

## Partitioning

1. 

