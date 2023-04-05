---
sidebar_position: 1
---

# About

## About this library

This  __C++__ library provides a framework to create **BehaviorTrees**. 
It is designed to be flexible, easy to use and fast.

Even if our main use-case is __robotics__, you can use this library to build
__AI for games__, or to replace Finite State Machines in your application.

__BehaviorTree.CPP__ has many interesting features, when compared to other implementations:

- It makes __asynchronous Actions__, i.e. non-blocking routines, a first-class citizen.
- Trees are created at run-time, using an __interpreted language__ (based on XML).
- It includes a __logging/profiling__ infrastructure that allows the user 
to visualize, record, replay and analyze state transitions.
- You can link statically your custom TreeNodes or convert them into plugins
which are loaded at run-time.


## What is a Behavior Tree?

A Behavior Tree (__BT__) is a way to structure the switching between different 
tasks in an autonomous agent, such as a robot or a virtual entity in a computer game.

BTs are a very efficient way of creating complex systems that are both modular and reactive. 
These properties are crucial in many applications, which has led to the spread 
of BT from computer game programming to many branches of AI and Robotics. 
 
If you are already familiar with Finite State Machines (__FSM__), you will
easily grasp most of the concepts but, hopefully, you will find that BTs
are more expressive and easier to reason about.

Think about the __Nodes of the tree__ as a set of building blocks.
These blocks are implemented in C++ and are "composable": in other words, they can be 
"assembled" to build behaviors.

![](intro_build_trees.svg)

In the image above, you can see as we are arranging these actions in a simple Sequence;
actions will be executed in order from left to right. To learn more, visit the page 
[Introduction to BTs](learn-the-basics/BT_basics.md).

### Main Advantages of Behavior Trees

- __They are intrinsically hierarchical__: we can _compose_
complex behaviors, including entire trees as sub-branches of a bigger tree. 
For instance, the behavior "Fetch Beer" may reuse the tree
"Grasp Object".

- __Their graphical representation has a semantic meaning__: it is easier to 
"read" a BT and understand the corresponding workflow. 
State transitions in FSMs, by comparisons, are harder to understand
both in their textual and graphical representation.    

- __They are more expressive__: Ready to use ControlNodes and DecoratorNodes
make it possible to express more complex control flows. The user can extend the
"vocabulary" with his/her own custom nodes.


## "Ok, but WHY do we need BehaviorTrees (or FSM)?"

Many software systems, robotics being a notable example, are inherently
complex.

The usual approach to manage complexity, heterogeneity and scalability is to 
use the concept of 
[Component Based Software Engineering](https://en.wikipedia.org/wiki/Component-based_software_engineering).

Any existing middleware for robotics took this approach either informally or formally,
being [ROS](http://www.ros.org), [YARP](http://www.yarp.it) and 
[SmartSoft](http://www.servicerobotik-ulm.de) some notable examples.

A "good" software architecture should have the following characteristics:

- Modularity.
- Reusability of components.
- Composability.
- Good separation of concerns. 

If we don't keep these concepts in mind from the very beginning, we create 
software that is tightly coupled and less reusable.

Frequently, the business logic of a software system is "spread" into many 
components and it is __hard for the developer
to reason about it and to debug errors__.

To achieve a strong separation of concerns, it is better to centralize
the business logic in a single location. 

__Finite State Machines__ were created specifically with this goal in mind, but in
recent years,  __Behavior Trees__ gained popularity, especially in the game industry.

