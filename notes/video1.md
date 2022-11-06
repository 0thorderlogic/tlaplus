# Intro VIDEO 

In the course: http://lamport.azurewebsites.net/video/intro.html

## What is TLA+?

A language for high-level modeling of digital systems.

**Digital systems include :**
	- Algorithms
	- Programs
	- Computer Systems

**High level means:**
	- At the design level
	- Above the code level

## What does TLA+ do?

It serves to model critical parts of digital systems,
while abstracting away less-critical parts and lower-level
implementation details.

Designed for CONCURRENT and DISTRIBUTED systems

Can help find and correct design errors
	- Errors Hard to find by testing
	- Before writing code

## Abstraction

Process of simplification by removing irrelevant details is called
abstraction. 

## Specifications

Precise high-level models are called specifications, sort of like a
blue print for code.

TLA+ can specify algorithms and high-level system design

## Basic Abstraction

An execution of a digital system is represented as a sequence of discrete 
steps

**Digital system :**
	We can abstract it's continuous evolution as a sequence of discrete events 

**Sequence :**
	An execution of a system is represented as a sequence of discrete steps

**Steps :** 
	TLA+ describes a step as a state change

**Execution :**
	An execution is represented as a sequence of states

**Behaviour :**
	A behaviour is a sequence of states OR execution.

			"""WE WANT TO DESCRIBE ALL POSSIBLE EXECUTIONS OF A SYSTEM"""
			"""WE WANT TO SPECIFY  ALL POSSIBLE BEHAVIOUR  OF A SYSTEM"""
## State change

> There are many ways to describe a digital system?!
	- Programming languages
	- Turing Machines
	- Many different kinds of automata
	- Hardware description languages

> But we can do better!
> We can abstract them all as **state machines**

## State machines 

	- All possible initial states
	- What next states can follow any given state
	- Halt for no more possible next state

**State :**
	A state is an assignment of values to variables

> Define state machine?

1. What the variables are
1. Possible initial values of a variables
1. A relation between their values in the current state and their possible values in the next state

```
#include <stdio.h>

int someNumber() // returns some number between 1 to 1000

void main() {
	int i = someNumber(); // pc = "START"
	i += 1; // pc = "MIDDLE"
} // pc = "DONE"
```

An obvious way to representing this program with a state machine is with:
a single variable ```i```;

[i:0] [i:42] [i:43]

> defining.....As a state machine

1. Variables: ```i```
1. Initial vales: ```i = 0```
1. The relation between the value of ```i``` in the current state and its possible values in the next state 
	> which cannot do done? Because another execution can yeild different results.

> Attempt PC = "PROGRAM CONTROL"

```
if current value of pc equals "START"
	then next value of i in {0,1,...., 1000}
		next value of pc equals "MIDDLE"
else if current value of pc equals "MIDDLE
	then next value of i equals current value of ```i + 1```
		next value of pc equals "DONE"
else no next value
```