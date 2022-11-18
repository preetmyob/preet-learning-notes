# Chapter 4 


## Context Mapping

- how you integrate bounded contexts
- usually reprents inter teams dynamics
- one way to think of it is as an adapter for the language of a single context
- Types of mapping/relationship

### Partnership

- two teams are closely aligned on the same larger goal and should interact frequently
- large emaphis on communications and synchornisation
- should last while advantagous
- larger commitement from both sides


### Shared Kernel

- an intersection of two domin models/bounded contexts
- teams agree to share the work in this area
- usually emerges during work rather than before
- requires very open communications
- can only exist if everyone agrees that this is better then each doing their own thing

### Customer-Supplier

- Supplier is upstream (U) and holds sway on delivery
- requires customer (is downstream D) to plan effectively
- often a common model for team relationshps in some organisations
- Generally occurrs where the culture doesn't allow Supplier to be autonomous

### Confirmist

- where a customer (U) has no desire to be led by supplier (D), so supplier just conforms to customer 
- exmaple is an affliate seller (conformist) of Amazon.com (upstream)
- here the downstream confirmist will adopt the language of the upstream context

### Anti-corruption layer

- One subdomain (D) introduces a formal translation between the two contexts
- Protect the downstream context isolate effectively from the upstream domain
- more expensive (akin to hiring a translator for the ULs)
- Allows the downstream domain to make best desicions for itself

### Open Host Service

- opposite of the Anti Corruption layer
- One domain creates a protocol that allows any other subdomains to inegrate with it
- Works very well with a conformist

### Published Language

- formal schema published by one domain that can be consumed by another
- works well with Open Host Service
- make UL translation easier 


### Seperate Ways

- No useful integration of the bounded contexts
- each context can create and manage their own UL

### Big Ball of Mud

- makes inegration extremely hard
- only heroics and tribla knowledge (speaking all ULs) is effective
- other subdoamins should use ACLs to protect themselves and shouldn't use the UL (!) of the big ball of mud
- 

## Using Context Mapping

### RPC/SOAP

- functions (procedure) focused
- tighter coupling of contexts unless OSJ/PL + ACL to reduce the UL proliferation

### REST

- resource focused
- web scaling proves it's effectiveness
- tighter coupling of contexts unless OSJ/PL + ACL to reduce the UL proliferation
- if you use REST and directly map the Agregates then you are basically enforcing a conformist relationship
- model agregates as synthetics on the use basis (create shapes for different use cases) and don't leak the domain composition

### Messaging

- Asychronicity and event driven using domain events
- reliable
- to avoid conformist mapping, rely on domain event schema and parsing and not domain even implementation
- messaging should be "at least once delivery"
- Listeners should be idempotent but have enough smarts to deal with receiving the same message multiple times when not needed
- this is more robust as it builds support for latency in from the start
 


