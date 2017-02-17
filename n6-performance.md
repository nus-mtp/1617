---
layout: page
title: On Software Performance
---

# Lecture 6: On Software Performance

This week, we will pay attention to the systems performance of your software.  This includes the running time, bandwidth, battery consumption, and storage.  Often, we have to make a decision to trade off between these different resources (e.g., use up more storage to reduce bandwidth).  Which resource to optimize depends on what is the most valuable.  In software that interacts with users, often we want to minimize the waiting time.

## Why is minimizing waiting time important?

* "“People will visit a Web site less often if it is slower than a close competitor by more than 250 ms.”" [from NY TImes](http://www.nytimes.com/2012/03/01/technology/impatient-web-users-flee-slow-loading-sites.html?pagewanted=all&_r=0)
* "Marissa ran an experiment where Google increased the number of search results
to thirty. Traffic and revenue from Google searchers in the experimental group
dropped by 20%." "we had a similar experience at Amazon.com. In A/B tests, we
tried delaying the page in increments of 100 milliseconds and found that even
very small delays would result in substantial and costly drops in revenue" [Merrisa Mayer at Web 2.0](http://glinden.blogspot.sg/2006/11/marissa-mayer-at-web-20.html)

There are some straight forward ways of reducing Web page load time, including reducing image size, remove redundant CSS, minimize your JS, etc.  Rather than these, We will focus on optimization that requires deep CS background.

## Rules of Performance Optimization

* Don Knuth says, "Premature optimization is the root of all evil."
* Ken Beck says, "Make it run, make it right, then, make it fast."

Don't think about optimization before you start coding.  Make the code work first, and then find out where is the bottleneck, and remove the bottleneck.

If the performance is reasonable -- do this after you have most of the features implemented.  If even you cannot stand how slow your code is,  you can optimize now.

## Profiling

Profiling involves running the code and collect usage statistics during run-time.  This typically gives you the time taken to call a function (or to execute a line) plus the number of times a function/a line has been executed.  Looking at the data, we might identify bottleneck within our code.

* Django comes with pretty good [profiling support](https://code.djangoproject.com/wiki/ProfilingDjango).  There is also [```silk```](https://github.com/django-silk/silk).
* For Ruby, see [here](http://guides.rubyonrails.org/v3.2.13/performance_testing.html)
* ```node``` has built-in profiler.  First run ```node``` with ```--prof``` to create a profiler's output, then run with ```--prof-process``` to produce human readable results.  [```v8-profiler```](https://github.com/node-inspector/v8-profiler) and [```node-inspector```](https://github.com/node-inspector/node-inspector) are useful as well.
* PHP users can checkout [```xdebug```](http://xdebug.org) and [```xhprof```](http://php.net/manual/en/book.xhprof.php)

```XCode``` and ```Android Studio``` comes with built-in profiler to instrument your code.

## Examples of Performance Issues

Once you find the bottleneck, you need to analyze the code and interaction between components to see what is dragging the performance.

Here are some of the common performance issues to pay attention to:
* Unnecessary disk I/O
* Unnecessary memory copies
* Unnecessary format conversion
* Unexpected interactions between system components
* Unnecessary locking
* Unnecessary SQL / database access
* Unnecessary network communication
* Bad data structures or algorithms
* Memory leaks
* Too much garbage for collection

## Common Tricks for Performance Improvement
* Pre-computation
* Caching
* Prefetching
* Pipelining / Parallelizing

## Performance Testing and Evaluation

As part of your project, you should profile your code and find the bottleneck (if any) and show how your optimize the code.  Here is a [sample section from CS3281/2 Team Polaris, AY 14/15](images/polaris-proj-report-6.1.pdf)

## Perception of Time

We have been looking at making the software run faster.  But often, for software
components that interact with the users, it is enough to make it _feel_ faster.

* A response time less than 200 ms is perceived to be instantaneous
* A response time less than 1 second is perceive to be immediate (noticeable, but easily tolerable by most users)

Make sure that page load is less than one second, and feedback to interaction
(e.g., clicking a button) is less than 1s.

## David Maister's [The Psychology of Waiting Line](http://davidmaister.com/articles/the-psychology-of-waiting-lines/):

###  1. Occupied time feels shorter than unoccupied time.

People who wait passively overestimate their waiting time by 36%.  So keep users active/occupied while waiting.  (e.g., start video playback while video is
loading; preload the next page while user is still in the current page).

###	2. People want to get started.

Example, starts video playback while downloading.  Render Web components that are downloaded first.

###	3. Uncertain waits are longer than known, finite waits.

Show users how long they will be waiting.

###	4. Unexplained waits are longer than explained waits.

Explain to the users what is going on.

###	5. Unfair waits are longer than equitable waits.

At least meet the waiting time of your competitors.

###	6. The more valuable the service, the longer the customer will wait.

Make your software more useful.

### 7. Solo waits feel longer than group waits.

## Perception of Value

Sometimes, making users wait would make them feel that the service they get is more valuable.  (Here's an example of [a placebo progress bar](https://www.youtube.com/watch?v=gpBWwl-Ngak#t=76))

## Latency Numbers
* What every programmer should know (http://www.eecs.berkeley.edu/~rcs/research/interactive_latency.html)
