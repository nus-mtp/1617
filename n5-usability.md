---
layout: page
title: On Software Usability
---

# Lecture 5: On Software Usability
10 February 2017

Berthil Muth recently said, ["nobody wants to use
software"](https://medium.freecodecamp.com/nobody-wants-to-use-software-a75643bee654#.uh4s8mza9).
What people want is to get things done.  To watch a movie, plan their study,
plan the curriculum, organize their bills, discuss during tutorials, make
connection at events, and prepare lecture notes.  While your project is
facilitating all these actions, your user interface stands in the way.  You
should design your interface to be as easy and pleasent to use as possible, so
that users can get their things done!

I have four general rules for user interface design:

## Rule 1: Don't Make Me Think

* Give clear, simple, useful, readable message/information/update/feedback to users
* Guide users on what to do
* Be consistent with what users expect
* Don't hide things that user may need
* Provide help, inline
* Place items logically (in context, grouped, hierarchically)
* The primary purpose of every page/view should be clear

## Rule 2: Don't Make Me Wait
* Provide visual feedback ASAP
* Tell users to wait (spinning beach ball, progress bar, DING! when done)

## Rule 3: Don't Make Me Work
* Provide shortcut for experts
* Set reasonable defaults
* Make expected actions easy to reach ([Fitts's Law](https://en.wikipedia.org/wiki/Fitts's_law))
* Allow direct manipulation

## Rule 4: Don't Make Me Cry
* Keep dangerous actions away
* Protect users work, always (allow undo, save a copy)
* Always provides a way out

How do you evaluate the usability of your software?  There are four methods:

## 1. Heuristic Evaluation

One way to evaluate and improve the usability of your software application is
to inspect carefully the user interface to see if it voilates a set of usability
principles (or heuristics).  Typically, a group of 3-5 evaluators will
_independently_ go through a list of guidelines and note down any
issue that they can spot.  They then combine their findings together.

One of well known set of heuristics is that from Jakob Neilsen.  I won't
reproduce it here, but you should read
[Jakob Neilsen's 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/)

## 2. System Usability Scale (SUS)

SUS is a relatively simple way to evaluate the usability of your application.
Unlike Heuristic Evaluation and Think-Aloud Protocol, it leads to a numerical
score that says how usable is your application.  It does not point out
specific issues and thus does not directly tell you how to improve your
usability.  As such, you should do this near the end of the semester as a way to
assess your usability.

Here is how SUS can be used.  First, you ask users to perform some common tasks
on your Website.  After a user is done with all the required tasks, you give
them a survey form with 10 questions with a 1 to 5 Likert scale (1 being
strongly disagree and 5 being strongly agree).

1. I think that I would like to use this system frequently.
1. I found the system unnecessarily complex.
1. I thought the system was easy to use.
1. I think that I would need the support of a technical person to be able to use this system.
1. I found the various functions in this system were well integrated.
1. I thought there was too much inconsistency in this system.
1. I would imagine that most people would learn to use this system very quickly.
1. I found the system very cumbersome to use.
1. I felt very confident using the system.
1. I needed to learn a lot of things before I could get going with this system.

Based on the user response, you compute a score.  Note that the odd number
questions above are positive questions (5 means good), while even number
questions are negative questions (1 means good).  To compute the overall score
from a given user, use the following algorithm:


    positive_score = (x1 + x3 + .. x9) - 5
    negative_score = 20 - ((x2 + x4 .. x10)-5) # flip
    total_score = positive_score + negative_score
    final_score = total_score * 2.5

where xi is the score for Question i.

Based on collected statistics over 500 evaluation, 68 is the average score.
Something above 80 is considered excellent, you should aim for a score of 80 and
above.

## 3. Think Aloud Protocol

In Think Aloud Protocol, you give a user a task to complete through your
application.  The user has to keep talking, telling you whatever come into his/her
mind while completing the task (i.e., _think aloud_).  You listen, watch, and note down what
difficulties they have when using your application.  The session is recorded so
that it can be replayed for analysis later.

Think Aloud Protocol is time consuming, but it allows you to uncover a specific
difficulty faced by users, and possibly why.  Such insights are not possible to 
get with the other methods.

Here is [an example](https://vimeo.com/1463808).

## 4. Quantitative Analysis

Quantitative Analysis involves collecting data and statistics about how users
use the application.  For instance, you can insert code in specific places to measure the
time taken for each step to complete a specific task.  You collect the statistics
for many users and identify the steps where it is the most time-consuming.  You
can count how many percent of the users have accidentally click on a button and then click
cancel when upon realizing the error.  

Quantative Analysis is useful when you have sufficiently large number of users.

## Your Tasks

For CS3283/4, you are expected to evaluate your usability using SUS, Think Aloud
Protocol, and Heuristic Evaluation, and to improve upon your UI based on the
findings.   These activities should be reported in your final report.

## Additional Readings

* Bruce Tognazzini's [First Principles of Interaction * Design](http://asktog.com/atc/principles-of-interaction-design/) (highly recommended)
* Jakob Nielsen's [10 Usability Heuristics for User Interface Design](http://www.nngroup.com/articles/ten-usability-heuristics/)
* The Nielsen Norman Group website has a treasure trove of articles on UI/UX design.
* Ben Shneiderman's [Eight Golden Rules of Interface Design](https://www.cs.umd.edu/users/ben/goldenrules.html)
* Joshua Porter's [Principles of User Interface Design](http://bokardo.com/principles-of-user-interface-design/)
* Peter Vukovic's [7 Unbreakable Laws of User Interface Design](http://99designs.com/designer-blog/2014/01/15/7-unbreakable-laws-of-user-interface-design/)
