# CHAPTER 1
## Reliable, Scalable, and Maintainable Applications

### *Thinking About Data System*

1. What is Data System (within the Context of Education), with examples?

A computerized system that houses and displays student, educator, and school information and allows users to retrieve, manage, and analyze the data. 
Examples of data systems include an assessment system, data mart, data warehouse, decision support system (DSS), instructional management system (IMS), 
learning management system (LMS) and more.

2. What are the three concerns that are important in most software systems?

Realiability, Scalability and Maintainability

### *Reliability*

3. What is the different between *fault* and *failure*? 

A fault is usually defined as one component of the system deviating from its spec, 
whereas a failure is when the system as a whole stops providing the required service to the user.

### *Software Errors*

4. Metion two examples of systematic error within the system:

* A software bug that causes every instance of an application server to crash when given a particular bad input. 
* A runaway process that uses up some shared resource—CPU time, memory, disk space, or network bandwidth.

### *Human Errors*

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

### *How Important Is Reliability?*

6.Why is it important to check our program for bugs?  How harmful can a bug be?  

Because a bug is a flaw in the software. And a bug can cause tremendous economic losses to companies or even loss of life.

### *Describing Performance*

7. What is the different between *latency* and *reponse time*?

The response time is what the client sees: besides the actual time to process the request (the service time), it includes
network delays and queueing delays. Latency is the duration that a request is waiting to be handled—during which it is latent, awaiting service





