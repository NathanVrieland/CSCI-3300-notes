# Design

## Give an example line of code that does not follow the design best practice recommendation: "Don't talk to strangers." 
- indirect objects are 'strangers'
    - foo.getA().getB().getC() 
        - sucks
## Given a pseudocode snippet: Identify the classes that are visible to the given class, and the nature (type) of visibility with each class. 
- visibility: ability to see, or have a reference to another object 
- A has vilibility to B if 
    - Attribute visibility: B is an attribute of A
    - Parameter visibility: B is passed as a parameter of A
    - local visibility: B is declared as a local object within a method of A 
    - global visibility: B is global to A
## Given a scenario, identify the GRASP design principle that needs to be applied to the problem. 
- Creator
    - Solution assign B to create instance of A if
        - B contains or aggregates A
        - B records A 
        - B closley uses A 
        - B has initalizing data for A that will be used to create A 
- information expert 
    - solution: use an information expert
        - information expert 
        - class that has the information necessary to fulfill the responsibility
- Controller
    - assign a respolsibility to a class representing 
        - the 'root' system device that software is running 
    - handles system events 
        - use same controller class for all system events in same use case
        - name your controller {useCaseName}Handler/Controller/session
            - similar to python's BaseHTTPHandler class
- low coupling 
    - how strongly elements is connected to and has knowledged of and relies on others
- High Cohesion
    - cohesion 
        - measure of how strongly related /focused the responsibilities of an element are 
- polymophism 
    - Benifits 
        - new variations are easy to add
        - new implimentations without effecting clients 
        - she doesn't mention this in the slides but: high code reuse 
- Pure fabrication
    - when you want to break high coupling and low cohesion, but other solutions like expert are not appropriate 
    - assign a highly cohesive set of responsibvilities to an artificial or conveninece class that does not represent a problem domain
- Indirection
    - when to assign a responsibility, to avoid direct coupling between two things
    - how to decouple objects so that low coupling is suported, and reuse remains high 
    - solution 
        - assign responsibilites to an intermediate object to maintain between other components or services that are not directly coupled 
        - this creates an indirection between two objects
    - maybe you have objects that need to offload data to a database or an API, so you might want to make an interface to do that
        - that way you can make different classes of that interface if you want to change API's or databases without changing the using classes 
- Protected variations
    - identify points of predicted variation ro instability 
    - assign responsibilites to create a stable interface around them 
## Given a scenario, identify the GoF design principle that needs to be applied to the problem. 
- Factory
    - factory is a pure fabrication object that handles creation 
- Singlton
    - define a static method that returns the singleton object 
- Adapter 
    - convert interace component into another one through an adapter object 
- Composite
    - define classes for composite and atomic objects implementing same interface 
- Facade
    - define a single point of contact with the subsystem
    - facade object wraps the subsystem 
    - single unified interface 
- observer
    - define a subscriber or listener interface 
    - subscribers impliment this interface
    - publisher can dynamically register interensted subscribers
- strategy
    - define each algorithm / policy / straegy in a seperate class, with a common interface
    - allows pluggable algorithms 
- caching
    - location transparency using service lookup
    - failover from remote to local 
    - loacl service partial repliocation 
---
## Consider the scenario where a Funds Transfer operation must be supported by an ATM, over Net Banking application, as well as in-person by a Cashier from a Bank branch  location. Which GRASP principle can best guide the assignment of this responsibility? 
- Sol: Polymorphism.
## In a Monopoly game, there are two dies. Each player plays both dies individually, gets die counts, and sums it to get the number of blocks to move forward for current  turn. To simplify, these individual operations are offloaded to a new class referred as ‘cup’ which plays all the dies and simply returns the sum. Which GRASP principle ## guides this design? 
- Sol: Pure Fabrication.
## Consider an application in which the given input needs to be formatted in several forms such as using newlines, tabs, as CSVs, etc. To support this requirement, the  format operation is defined as part of an interface IFormat which is implemented by various text formatting classes such as NewlineFormat, TabFormat, CSVFormat, etc.  Which GoF pattern recommends this design? 
- Sol: Adapter.
## Consider an application which handles both general as well as private/personal information. Based on the type of data being handled, the system dynamically selects an appropriate data encryption approach to securely store the data. Identify the GoF pattern which can guide the system design for this requirement.  
- Sol: Strategy.
## Consider an application which prints the given text in specified format. If the text is a single character, then the character is formatted as required and printed.  Otherwise, if the text is multiple characters, then the first character is processed as earlier, and the prior procedure is called recursively on remaining text. ## Finally, the complete text is returned in required format. Identify the GoF pattern which can guide the system design for this requirement. 
- Sol: Composite.
## Consider an application which has several clients which submit tasks to be processed by multiple servers. Identify the GoF pattern which allows the clients and servers to execute in an asynchronous manner, facilitating low coupling. 
- Sol: Observer.

# Testing concepts

## Briefly describe the purpose of the various types of Testing: Functional / User / Performance / Load.
- Functional testing 
    - test the finctionality of the overall system 
    - discover as many bugs as possible 
    - povide convincing evidence tha the system is fit for its intended putpose 
- user testing 
    - test that the software product is useful and usable by end users
    - show that users understand how to access the software's features and use them
- preformacne and load testing 
    - test that the software works quickly and can handle the expected load placed on the system
- Security testing
    - test that the software maintains its integrity and can protect user information from theft and damage 
## List the four goals (focus) of system testing. 
- discover if there are unexpeced and unwanted interactions between the features of a system 
- discover if the tthe system features work together effectivley 
- make sure it operates int he expected way in the different enviorments it will be used in 
- test responsivness, througput, security, and other quality attributes 
## List the various stages of test-driven development approach.
- identify partial implementaion
- write mini unit tests
- write a code stub that will fail tests
- run all automated tests 
- impliment code that will cause the failing tests to pass
- rerun tests
- refactor code if required 

# Testing approaches

## Briefly describe and compare the concepts: Exhaustive testing and Selective testing
- in the example program, with 2 loops and 3 conditions, there were 10^14 possible paths
- exhaustive testing is impossible it would take 3170 years
- selective testing
    - test the most used and most important paths of a program 
## Based on the software development best practice recommendations discussed, who is preferable to perform testing: Developer or an independent tester? Explain briefly. 
- developer 
    - understands the system and overlooks issues 
- independent tester
    - must learn about the system and will attmpt to break it 
- independent tester  should test a system for best results
## Briefly compare the concepts: Structural/White box testing and Functional/Black box testing
- white box
    - knowing the internal workings of a program, tests can be conducted to assure that the internal operation preforms according to spec
    - tests based on internal structure 
- functional (black box) testing 
    - Knowing the specified functions that a procuct has been designed to preform 
    - demonstrate it is fully operational
    - based on external behavior as well as internal structure 
## Given a pseudo-code snippet, draw the corresponding program graph. 
## Given a program graph with, compute the maximum (P*) number of execution paths possible from the entry node to the exit node. 
- for sequential parts, P* is multiplied 
- for conditionals, all branches' P* are added
- for loops the P* of the loop body is raised to the power of the number of loops
- for indefinite amount of loops, the P* of the loop is computed for all possible number of iterations and added together
## Given a program graph, identify the independent (IP) paths. 
###     Note: The number of IP paths in a program graph is the same as the number of (simple) condition nodes in the graph plus one. 
###     Note: All IP Paths are unique paths. In other words, each new IP path should include at least one node that was not included in the prior identified IP paths.
###     Note: All IP paths start at the entry node and end at the exit node.
## Given a program graph, a set of IP paths, and the conditions, identify test cases.
##     Note: Refer to slide #31 for example discussed. 
## List two limitations(problems) of IP Path coverage (testing approach).
- Loops not tested thoroghly
- data structures may not be exercised fully
## Idea: "Not all test cases are created equally" - Explain. 
- A randomly selected set of test cases is statistically insignificant
- Some test cases give more info than others
## Given a program graph comprising nodes marked with DEFine and USE of variables at those nodes, identify the DU-Paths.
###     Note: DU-path for a given variable X is the sequence of nodes in the path from the node where the variable X is assigned a value, to the node where the value of  variable X is accessed, in other words, path from DEF(X) to USE(X). Note that, any DEF(X) will invalidate the prior DEF(X).
###     Valid DU path e.g. M2(DEF X) – C3 – M4 – M5 – C6 – M7(USE X)
###     Valid DU path e.g. M2(DEF X) – C3 – M4 – M5 – C6 – M7(USE X) – C8 – M9 (USE X): Note: X is not redefined after line#2
###     Invalid DU path e.g. M2(DEF X) – C3 – M4(DEF X) – M5 – C6 – M7(USE X) --> The valid DU path for this is, M4(DEF X) – M5 – C6 – M7(USE X).
## Briefly compare the concepts: Test-to-Pass Vs. Test-to-Fail
- Test to pass
    - make sure software minimally works 
    - not trying to push the limit
    - simple cases 
    - not to find bugs
- test to fail
    - done after test to pass
    - trying to break software
    - find bugs
    - force errors
## Given a condition expression, list the equivalence partitions for input variable. 
` if (x = 5) `
- equivalcance classes
    - `x < 5`
    - `x > 5`
    - `x = 5`
`if (x > 5 && x < 10)`
- equivalence classes 
    - `x <= 5`
    - `x x > 5 && x < 10`
    - `x >= 10`
`if (x in <array>)`
- equivalence classes 
    - `x in array`
    - `x not in array`
`if (x == true)`
- equivalence classes 
    - `x is true`
    - `x is false`
# Reliability

## Provide a brief overview of the three techniques to improve software reliability
- fault avoidence 
    - avoid introducing faults into the program
- input validation
    - validate that all inputs conform to expected format
- failure measurement
    - ensure program failures have minimal impact on users 
## List the complexity reduction guidelines/approaches for the following: 
- complexity reduction
    - structural complexity 
        - how hard it is to understand the program
        - functions should do one thing only
        - no side effects
        - classes have single responsibility
        - minimize enheritance trees 
        - avoid multiple inheritance 
        - avoid threads unless necessary 
    - data complexity 
        - representations of daa and relationships between elements
        - define interfaces for all abstractions 
        - define abstract data types
        - avoid float types
        - never use data aliases 
## Briefly describe the concept of refactoring, and how it helps improve the quality of software. 
- changes and additions increase complexity 
- refactoring
    - chaning a program to reduce complexity 
    - doesnt change behavior
    - reduces reading complexity 
    - makes the program more understandable 
    - makes it easier to change 
    - redcues chance of making mistakes when you introduce new features
## What is a code smell? Provide some examples of code smells, and refactoring actions to overcome the problem.
- idicators in the code that there might be a deeper problem 
- type and fixes
    - large classes 
        - break them down
    - long methods 
        - split into smaller fucntions
    - duplicated code
        - make into functions
    - meaningless names 
        - refactor into better names 
    - unused code 
        - delete it (you can always get it back from git)
## Briefly describe the four methods of implementing input validation.
- checking that 
    - users input is in the correct format 
    - input value is within range 
- critical for security and reliability 
- define rules for every type of input field 
    - if input does not pass, reject the input
- methods 
    - built in validation functions
        - lots of frameworks have stuff like isEmail() isInt() isDate() and stuff like that
    - type coercion 
        - stuff like int() in python
    - explicit comparisons
        - check against all possible values or range
    - regular expressions
        - powerful syntax for defining inputs
## List four measures to minimize effect of failures.
- persistant data should not be lost or corrupted
- user should be able to reciver work done before failure
- software should not hang or crash 
- always 'fail secure' so that confidential data is not left in an unsecure state
