# What is an architecture?
The term _architecture_ in software development refers to the basic design i.e a blue print decided by the developer to frame his application.
Developers decide the architecture for their applications based on the idea to achieve their desired goals from the applications.

## Some types of architectures
* Blackboard 
* Monolithic 
* Microservices
* Data-centric
* Space-based

### Microservice architecture
This architecture is inspired from the modularization concept that was previously implemented on monolithic architecture but due to ever-growing size of data the modularity faded and the ultimate goal of **loosely coupled & highly cohesive** service failed to complete.

#### Pros of using _microservices architecture_ ####
This newly adapted architecture changed the paradigms of software development and provided various advantages that affected the whole industry and most of the applications switched to this architecture.Some shifted because of the variety of functions it offered while others followed them to stay in market against their competitors.
* This architecture provided the opportunity to scale-out the size of the aplications horizontally instead of scaling-up them vertically
* It fasten-up the update cycle of the applications through CI/CD pipelines through which you can update within days
* It provided more resource efficient designy
* It allowed to work on different modules of the application simultaneously
* It also releived developers to avoid massive amount of code in monolithic artichecture
* It offers polyglotting making it convinient for developer to choose desired programming language on different modules


 #### Trade-offs of _microservices architecture_ ####
Obviously ,it also has some downsides in contrast to the benefits it provide ranging from design complexity and distribution problems.
* Many times applications ended up pathetically when shifting from monolithic to microservice architecture
* Due to design complexity , any small change made to one of the modules can affect the whole application if not fixed timely
* Any bug in the module can result in data inconsistency
* It provides a variety of solutions to different problems but making any wrong decision can terribly affect your application
* Due to stateless condition it offer challenges to developer to sync the modules together due to distribution complexity in contrast to monlithic.
* Security is one of the most overlooked aspects of development,it is more challenging to secure the largely distrubuted units of the application

#### Conclusion ####
Microservices architecture provided the solution for the growing problems and filled the vacant space in industry by providing certain features giving a new shape to software development.At last its the choice of the developer to go with any architecture that fulfills his requirements providing convenience to him
