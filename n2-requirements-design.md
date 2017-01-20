---
layout: page
title: Software Requirements and Design
---

# Lecture 2
20 January 2017

There are three parts to this lecture. 

## In-class Exercise on Software Requirements

Last week, I talked about the ten desirable properties of software requirements.
In this lecture, we get some practice about this.  

Here is a preliminary software requirements taken from one of the past projects
for you to comments on what's good about the requirements and what's there to
improve upon, based on the ten desirable properties:

* [Sample Requirements](n2-sample-requirements.html)

## Including Security Consideration in Software Requirements

Building a secure system is more than adding "The system should be secure" as a non-functional requirement.
Some functionalities have to be included into the system to ensure the security of the system.  Security is not a feature.  It is a property that emerges after sufficient number security-related mechanisms are implemented.

Security can often be included as a constraint (e.g., "precondition: user must
be authenticated" for a "transfer money" use case).  Another way security can be
specified is by listing the anti-behavior, i.e., list down what users should
_not_ do.  We then counter these anti-behavior with added constraints or functional requirements.

One way to think about security is to consider the different categories of threats:
	 + **S**poofing: can the user pretend to be someone else?
	 + **T**ampering: can the user tamper with the data?
	 + **R**epudiation: can the user deny ever performing an action?
	 + **I**nformation disclosure: can the user see something he/she is not
supposed to see? 
	 + **D**enial of service: can the user overload or crash the system?
	 + **E**levation of privilege: can the user gain more privilege than
intended?

### Example: Initial User Stories

1. As a __customer__ I want to __login with my username and password__ so that
__I can access my bank account online__ 
2. As a __customer__ I want to __transfer money to another account after I
login__
3. As a __customer__ I want to __be able to logout after I login__
4.  As a __costumer__ I want to __reset my password when I forgot what my
password is__ so that __I will not lose access to my account__.

### Example: Abuser Stories

We will fill this in during class

## Software Design

If your team already has sufficient ideas about __what__ to implement for your
project, it is now time to think about __how__ to implement it.  This step is
where you _plan_ your implementation details, from what are the major components
of the system, what languages/libraries/frameworks/databases to use, what
algorithms/data structures to use, what the UI would look like, what are the key
tables in your database, etc.  You may even start a small prototype to explore
the options you have.  

For your project, the design and architecture are expected to change over time.
You should, however, still have _sufficiently detailed and stable design_ to
move on to the implementation phase. 

Key decisions to be made during the design phase are:
+ which framework/library to use?  
+ what platform to support? 
+ what’s the database schema?
+ what the UI looks like?
+ what are the major components? how do they interact? 
+ what are the APIs?

#### What type of architecutral diagrams to draw?
+ no fix rules here, just be simple, clear, and consistent
+ can have more than one: 
    + one for development view (classes, tables, etc)
    + one for physical view (server, phones, laptops, etc)
    + one for logical view (server, client, database, etc)
+ be very clear yourselves what boxes and arrows mean
+ common mistake: e.g., an arrow means inheritance in some parts of diagrams,
means the sequence of flow in other parts, and means passing data from one
component to the next in yet another part.
+ common mistake: arrows without labels
+ rules of thumb: if a diagram is not readable on 1-page A4 print out, it is not
useful 
