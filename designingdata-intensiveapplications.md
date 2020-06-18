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

Cypher is a declarative query language for property graphs, created for the Neo4j graph database