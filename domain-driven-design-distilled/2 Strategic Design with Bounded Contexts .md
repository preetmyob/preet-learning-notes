# Chapter 2

You get the *Big Ball of Mud* when you don't constrain the the number of concepts within your context. You can limit this by using bounded contexts. 


## Bounded Context 

- semantic boundary in which everyone uses the same (ubiquitous) language
- the strategic one for your company is the most important bounded and is called core domain
- the modelling that we do results in the domain model
- one team works in a Bounded context
- the software software, data, schema and  and modelling remain within the confines the ownership of the bounded context
- Words used in other bounded contexts are not the same though they may look identical 
- allows testing to be smaller due to constraints on context
- bounded by input and output adapters

### Ubiquitous Language

- Clear and precise to all team members and domain experts. 
- Rigour allows lower impedance to communication and reduced miscommunication
- allows team to focus on the business complexity not the technical complexity
- dont just pick nouns for your UL, use scenarios. For instance consider the backlogItem example. *Allow all backlogItems to be commited to a sprint. It can only be commited if it already scheduled for release. If it's already commited to a different sprint, it must be uncommited first. When the commit completes (uncommited or commited elsewhere) notify the interested parties*. 
- the ul may change a lot early on, as it it refined. However that doesn't mean it cannot be refined many years later

### Domain Model 

- should be free of technology
- documents and diagrams are not part of the domain model. They may assist in understanding, but the code is where the domain model lives. 
- by making the domain model in code, we can use executable tests as the specification, and the tests should by definition be readable by the domain experts. This gives us acceptance tests for the model   
- contains entities 
- executes business logic 
- emits domain events

### (Application) Services

- code that isn't part of the domain model
- 

## Microservices

- you can consider the a single bounded context to be a single or multiple deployable units, but they are logically one microservice from the point of view of the semantic boundary of the context.


## Questions

- how does language work across bounded context, e.g. at their boundaries?
- can we say that business logic is just code that represents the change in state of entities? *i.e. application services represent stuff happening and business logic is executed when appication services deliver domain events to   (from outside/inside?) to entities*


- 
