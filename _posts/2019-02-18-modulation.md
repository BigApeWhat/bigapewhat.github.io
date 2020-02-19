---
layout: post
title: "Modulation"
permalink: /blog/:title
date: 2020-02-18 20:00:00 -0700
categories: [development]
---
## Modularity
Grouping of related code are composed into individual units when put together create a complex structure | A Module. There are 3 C's to keep in mind when creating modules, Cohesion, Coupling, and Connascence. Keeping these factors in mind when developing will help writing clean and understandable code.  
<!--more-->

## Cohesion
Defines what parts of code are similar/related enough to be part of the same module. If these units of code would be separated it would increase coupling because they depend so much on each other. 

###Types of Cohesion
Functional cohesion - Most of a module is related to another, in which one contains essential parts for another to function properly.

Sequential cohesion - One outputs data that becomes the input for the other.

Communicational cohesion - Each module share the same information or contributes to some output. For example, add a record to the database and generate an email based on that information.

Procedural cohesion - Executes code in a particular order.

Temporal cohesion - Based on timing dependencies.

Logical cohesion - The data within modules is related logically but not functionally. "StringUtils"

Coincidental cohesion - Nothing is related except that they are in the same module

## Coupling
When 2 or more modules are dependent on one another when executing functions. Abstract class decreases coupling while concrete increases it.

### Measuring Component Stability (Dependencies)
Fan-in = incoming dependencies = # of classes that depend on component
Fan-out = outgoing dependencies = # of classes that component depends on
I = fan-out \ (fan-in + fan-out) = (1 means maximally unstable, 0 means maximally stable)
(We don't want all components to be stable cause they would be unchangeable)

### Measuring Component Abstraction
Nc = # of classes in component
Na = # of abstract classes and interfaces in components
A = Na / Nc (0 means no abstraction, 1 means maximum abstraction)

### Relationship
(0,1) = stable and abstract
(1,0) = unstable and concrete
(1,1) = Highly stable and concrete (The zone of pain – only if volatile – String class is non-volatile)
(0,0) = Highly unstable and abstract (The zone of uselessness – has no dependents

## Connascence
If a change in one component requires a change in another. 

### Static Connascence - source code
Connascence of Name (CoN) - Multiple components must agree on the name of an entity.
Connascence of Type (CoT) - Multiple components must agree on the type of an entity.
Connascence of Meaning (CoM) - Multiple components must agree on the meaning of particular values. 1 = true, 2 = false
Connascence of Position (CoP) - Multiple entities must agree on the order of values.
Connascence of Algorithm (CoA) - Multiple components must agree on a particular algorithm.

### Dynamic Connascence - runtime
Connascence of Execution (CoE) - The order of execution of multiple components is important.
Connascence of Timing (CoT) - The timing of the execution of multiple components is important. 
Connascence of Values (CoV) - Occurs when several values relate on one another and must change together. 
Connascence of Identity (CoI) - Occurs when several values relate on one another and must change together.
