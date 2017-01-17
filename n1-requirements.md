---
layout: page
title: On Software Requirements
---

# Lecture 1: On Software Requirements
13 January 2017

### Introduction
* The user requirements specify what your end-product can do / what the customer
* wants
* Functional / non-functional requirements
* Many tools for requirement gathering:
    * brainstorming
    * user survey
    * observation
    * interviews
    * focus groups
    * prototyping
    * analyzing related software
* Use whatever tools suitable for your project

### Why Good Requirements Important?
* Helps to define the goals of the project
* Helps to communicate among team members and with customers
* Serve as a contract (for CS3283, can change later)
* Helps to determine test cases and evaluation criteria
* Helps to plan projects (estimate time, prioritize features)
* Helps to reduce bugs
* Leads to better software design

### Properties of Good Requirements
* Adapted from [Scott Sehlhorst’s Top Ten
* Rules](http://tynerblain.com/blog/2006/05/25/writing-good-requirements-the-big-ten-rules/) 
   1. Correct -- of course
   1. Valuable — put in requirements that are of good values to the users; solve
their problems; support their strategy, etc.
       * prioritize the requirements (must-have, good-to-have,
       * only-if-time-permits, etc)
   2. Easy to read — write for people with diff background; use figures;
scannable; cross-references, etc.
   3. Design free — focus on what, not how
   4. Attainable - don't put in things you can't attain
       * e.g., "analyze 100 video cameras in real-time"
       * e.g., "store up to PB of data in the cloud"
   5. Complete - doesn't leave out anything, consider error cases, external
systems 
   6. Consistent — don’t put in impossible requirements, use consistent terms
       * e.g., "device"/"phone"/"mobile" -- are they the same or not.  Establish
       * a project glossary will help. 
       * e.g., "only administrator can edit X", else where, "any user can edit
       * X"
   7. Unambiguous - cannot be interpreted differently by different people 
       * e.g., avoid "the user",
   8. Verifiable - can be verified within your means (finite, cost-effective way
to verify)
       * e.g., avoid "easy to use", "should work most of the time" 
   9. Atomic — cannot say “half of this requirement is implemented”
       * e.g., "user can post text, URLs, or photos to their wall." 

### User Stories vs Use Cases

User stories and use cases are two popular ways to document software requirements.  

* *User stories* specify the software requirements from the viewpoint of the
user and comes in the form of "as _someone_ I want to _do something_ so that
_something happen_".  Additional conditions of satisfaction can be added after
this sentence.   User stories are easier for users to read.

* *Use cases* specify how the user interacts with the system.  It is structured
into different sections (systems, actors, pre-conditions, post-conditions,
main success scenarios, extensions).  Use cases can be converted into code
more directly than user stories.  A *use case diagram* provides an overview of
the possible interactions between different actors and the system.

You are free to choose whether you want to use user stories or use cases.

