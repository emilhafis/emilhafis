---
description: >-
  In this video I want to tell you about the next important BPMN building
  block.  This is the next type of Gateways called "Parallel Gateway", very
  commonly called "AND" (Gateway). It looks like a diamo
---

# Parallel Gateway (AND)

In this video I want to tell you about the next important BPMN building block.

This is the next type of Gateways called "Parallel Gateway", very commonly called "AND" (Gateway). It looks like a diamond with an

plus marker inside.

It allows you to split and merge parallel paths.

This is called synchronization and we'll cover this in a second.

You need to know two very important things about parallel gateways.

First one is that each path gets a token.

We don't need any conditions.

Each path will (always) get a token.

And second: all parallel paths must complete before synchronization allows the process to continue.

So all the work needs to complete before our process can continue.

Parallel Activities i.e. Tasks and Sub-processes may take place at the same time,

if they have different performers but this is not important thing. What is important: all elements

need to complete before we can continue.

And as for a naming this is rather simple.

Since we don't check any conditions we don't usually show name neither for the Gateway nor for the outgoing

Sequence Flows.

So this is rather simple. And now: how does it look like? Our case of \[Tasks named] ABCDEF would be a little bit different

if you'd like to show the "I want it all" case \[i.e. that all Tasks must take place].

So, our token is born and after we completed task A, interesting thing happens.

Please take a look: here we have one token and now voilà.

It was copied.

So we have 3 independent tokens that are ready to follow the Sequence Flow.

Let's assume that task B takes shortest (time) to complete.

So this is the fastest one.

So after it (Task B) was done our token continues but we cannot follow.

We cannot perform E and F because synchronization requires that all the tokens that were created - in

this case 3 - will need to meet (together) to be merged into 1 \[token], so that the process can continue. So, after

we finished C we have 2 of the 3 tokens.

so we still cannot continue. \[But, after D was done] since the last element finally finished

Now those 3 tokens can be synchronized and our process can continue.

So this is very important

thing about Parallel Gateways.

You will be splitting and merging parts and very importantly you will need to understand how the tokens behave.

If you take a look at a process like this,

Valid logs could be for example: ABCDEF or assuming that we took it in a in a slightly different

order.

It would be ABDCEF or maybe ACBDEF, but it only is a matter of order

how those tasks were performed. We would not be able to say that our log was let's say ABCEF

because until this \[Task D] is done our token cannot continue synchronization will not allow it.

So this is very important thing to know.

It is not allowed to skip any of the elements from the parallel paths.

Autoscroll

###

### Course content

### Overview

### Q\&AQuestions and answers

### Notes

### Announcements

### Reviews

### Learning tools

\
