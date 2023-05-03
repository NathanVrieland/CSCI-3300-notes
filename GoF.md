# Gang of Four design patterns
## Abstract 
- who creates the adaptors?
- how to determine which class of adaptor to make 
- design principle 
    - different groups of objects responsible for connectivity to external systems
- advantages 
    - seperates responsibility of complex  creation into cohesive helper objects
    - hides complex creation logic 
    - optomized memory managment
- factory is a pure fabrication object that handles creation
## Builder
## Factory method
## prototype
## Singlton
- problem 
    - exactly one instance of an object is allowed
    - object needs global, single point of access
- solution 
    - define a static method that returns the singleton object 
## Adapter 
- how to resolve incompatable interfaces or provide stable interface to similar components with different interfaces
- solution 
    - convert interace component into another one through an adapter object 
## Bridge 
## Composite
- how to treat a group or composition structure of objects the same way as a non-composite object
- soluton
    - define classes for composite and atomic objects implementing same interface 
## Decorator
## Facade 
- common, unified interface required
- undesirable coupling to many things in subsystem
- implimentation of subsystem may change
- solution
    - define a single point of contact with the subsystem
    - facade object wraps the subsystem 
    - single unified interface 
## Flyweight
## Proxy
## Chain of responsibity
## Command
## interpreter 
## itorator
## mediator
## memento
## observer
- problem
    - subscriber objects interested in state changes and events of publisher object 
    - they will react in their own way 
    - publisher wants to maintain low coupling with subscribers
- solution 
    - define a subscriber or listener interface 
    - subscribers impliment this interface
    - publisher can dynamically register interensted subscribers
## state 
## strategy
- how to design for varying, but related algorithms and policies 
- how to design for the ability to change these algorithms or policies 
- solution
    - define each algorithm / policy / straegy in a seperate class, with a common interface
    - allows pluggable algorithms 
## template method
## visitor
## ID's to objects
## caching
- reovery from remote service failure 
- solution
    - location transparency using service lookup
    - failover from remote to local 
    - loacl service partial repliocation 
## exceptions
- add info to be contexually meaningfull
- name the problem not the thrower
    - looking at you java
    - assign name based on why the exception is beign thrown 
    - easier to understand the problem 
    - similarity of classes of exceptions 
## centeralized exceptions 
- centralized 
    - singlton error logging object
- distrobuted system
    - each local singleton will collaborate with central error logger
- benifits 
    - consistancy 
    - flexible definitions of output streams