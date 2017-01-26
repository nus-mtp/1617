---
layout: page
title: On Software Architecture and Planning
---

# Lecture 3: On Software Architecture and Planning
27 January 2017

There are three parts to this lecture:

* Agile incremental delivery
* Good software architecture
* Sprint planning

## 1. Agile Incremental Delivery

We are going to structure your sprints based on the spirit of Agile Incremental Delivery.  By the end of each week, there should be a "potentially shippable" version of your project deployed and ready for me (and other users) to use and test.

What is considered as potentially shippable?  It should

- be as robust (bug-free) as possible
- contain features that are as valuable to the users as possible
- be integrated

In your earlier deliverables, the UI might not be polished yet,
the database might not be properly setup yet (e.g., you can store information in a file),  the core algorithm might not be accurate or optimal, that's OK.

We will discuss this using Facebook and IVLE as examples during class.  

You are expected to continuously polish, tweak, enhance the software over the semester.  You will likely be replacing one component with another, improving the internals of a component, etc.  To minimize work and bugs, how you design the architecture of your project is going to be important.

## 2. Software Architecture

The two utmost important principles for good software architecture design are _low coupling_ and _high cohesion_.  Low coupling means that you should structure your software components so that there are as little dependencies as possible between the components; High cohesion means that functions that are closely related to each other should belong together in the same component as much as
possible.

If you follow these principles during your design, then the emerging
architecture should be high on:

1. *Modifiability*: You should be ready to swap out one component and
replace it with another, with minimal change.  You should allow for internal changes to one component, without affecting other components.  You can delay a design decision as long as possible.

2. *Testability*: Each component should be easily tested individually without relying on the other components (e.g., without UI and without DB)

3. *Reusability*: The component should be reusable in other context/systems, and by multiple other components in the same software.

### Common issues with software architecture from past experience

This is taken from last year, and so far I have seen the same issues this year.

1. The software architecture depicts high-level components that are responsible for many unrelated tasks.

    To increase the cohesion of your design, a component should perform a small number of highly-related tasks. Try this: write down, as detail as you can, what each component in your architecture is supposed to do. For instance, just saying "contains logic for DB" or "relay messages between UI and logic" is not detailed enough. You should write down what type of logic is there, and what messages are relayed, etc.

    If you find that you have to write down many unrelated tasks, then this is a sign that you should further partition the component into smaller components.

    As an example, if your component performs the tasks: (i) searching for the interested users in the database, and (ii) checking for users access right to the database, then instead of one "logic for DB" component, you can partition it into two, one called "User Finder", the other called "User Access Controller."

2. The architecture diagrams depict arrows without labels.

    The meaning of the arrows in the diagram should be clear. Are they depicting dependencies? Data flows? The sequence of invocations? Or something else?

    You should decide what the arrows mean, then properly label them if it refers to the data flow between the components.

    Similar to Item 1 above, if you find that you arrows capture too many types of data flowing between two components, then you should split the components and/or arrows.

    One should be able to evaluate the amount of coupling between the components (and what resulted in the coupling) by looking at the architecture diagram. If the components and arrows are too high level, then the coupling might not be visible, and this gets into the way of improving your design to remove the coupling.

3. Pay attention to your domain logic and application logic.

    I noticed that many of the proposed software architectures focus on the CRUD operations of the data. To me, this portion of the software architecture, in a large part, is determined by the framework/platform chosen.

    What is more interesting and harder to decide, is how to fit your
application/domain logic with the rest of the components, how to decompose the logic into smaller components with low coupling and high cohesion. Most teams did not pay sufficient attention to this in the beginning.

4. Choose meaningful names.

    It is tempting to name your components "Something Manager," "Something Controller," "Something Logic," etc. These are generic names that do not reflect what each component is doing. It is a sign that the responsibility of the component is either not well thought out, or it has too many "rojak" responsibilities that you can find a good name.

    Writing down the responsibilities of each component explicitly, as in Item 1 above, will help you to find the right agent noun to call the component.

5. Overuse of the Facade pattern.

    Some teams have used the facade pattern to communicate between client/server, or different layers of the architecture.

    The facade pattern is useful to hide the complexity of the underlying
components. It is most useful when we do not have access to, or ability to modify, the underlying components (e.g., we use an external library).

    Most of the usage scenarios of the facade pattern in your design, however, does not fit into the use cases, and the facade could be removed to expose the underlying components directly. If indeed the exposed components are too complex, then you should consider redesigning and simplifying the components first, before adding a facade over them to "sweep the complexity under the rug".

## 3. Sprint Planning

Since you will start your implementation in Week 5, you should spend some time planning for your sprints.  For a successful sprint, your team should prioritize your tasks based on their dependencies among each other, the importance and the value of each feature, and the _estimation_ of the effort needed to complete the
tasks.

I suggest that you plan for one sprint at a time.

Translate your user stories into tasks.  Sometimes, you will notice that one user stories can be broken down into smaller tasks (i.e., your initial
user story is not atomic).  

Each task should fit into one sprint, if not, try to break it down into smaller tasks.

## 4. Tasks for Week 4

* Continue to refine the requirements
* Continue to refine the design
* Plan for your Sprint 1: What should be the deliverable for Week 5?  What are the tasks needed to achieve that?
* Get familiarize with the framework/library that you plan to use
* Setup GitHub, Travis, and Heroku so that you have a simple skeleton app deployed.
