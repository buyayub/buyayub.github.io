---
title: My Progamming Language
---

My writing on "reigning" a computer comes with a great question: where on earth do I start? The issue comes by the chasm between application and theory, and the many bridges crossing it.

After a bit of soul searching, I thought the funnest way to start is by writing my own programming language. I can use the language to create libraries in that language, applying to whatever domain of computer science I can think of. So if I'm learning data structures and algorithms, I'd find use writing for my language there.

It's all just assembly in the end.

But I never do good with blank slates, for as soon as I start to imagine, I start climbing mountains. It doesn't help that I'm reading on ontology now, and so the thought of creating a programming language has me enter into questions about meaning, entities, causation, and so on.

It's become overwhelming how similar yet different everything is: Name, variable, symbol, pointer, reference, object. I don't know where to start and where to begin.

I also asked myself, is code, data, and is data, code? It feels a perverse coupling. It's like saying time is a substance. But it is, isn't it? When we look at a function, we can create a derivative from, showing substantive representation of its change. Likewise, if we say x is position, and y is time, then isn't y itself a substance as much as a position is? But no, position is an attribute.

The functions of x and y can't be entities, but attributes rather. The height of something over time, the height of something with respect to its distance from something. A relation is between the attributes of an entity. So time another attribute?

My head hurts. I'll leave my own philosophizing for later, as I respect the field and I want to read more to catch up on its discussion. I don't want to corner myself into more preconceptions than I already have when approaching it.

But that doesn't help me figure out my programming language. I'm granted time, for now, to simply take in knowledge on programming language. I'll want to go back to linguistics and learn some syntax. I'll also want to spend some time with interesting languages like Lisp and what not. It gives me opportunity to imagine the perfect language I could try to implement.

## Type System

I dislike the idea of native type systems, and I want to go to as basic as I can get it. In assembly, you are (typically) thrust upon three inherent types of data to which operations are provided for: integer, logic (bitwise), and floating point.

What I mean by that is: you have integer operations (in binary representation), you have bitwise operations (logical operations), and you have floating point operations (`fadd`). I don't know why people keep answering that assembly doesn't have native types. If it has operations done under an assumed representation, it has native data types. 

I think my confusion comes from the fact that I got used to implicit variable types in langauges like Python and JS, so I don't see type restriction inherent in typing systems anymore. Regardless, anyone who uses assembly will recognize that someone using integer operations on a floating point value will muck up their numbers, so I declare that types are implicit in contemporary assembly, and the only pure non-typed instruction set would be one that purely uses bitwise operations.

The addition of the other two types creates a bit of efficiency and complexity. I'd love to write in pure logic but I'd be a bit insane to implement addition using bitwise operations when I can just use an add instruction natively. It's far more efficient too, since bitwise operations work on the whole byte.

Same goes with floating point arithmetic. So it seems you need to use those data types in assembly.

However, *my language* doesn't need to. Individual bit operations provides the basic form of all circuit operations. The issue would be to create a compiler that can recognize bitwise operations as other forms of instructions, and optimize for it. It shouldn't be too difficult, I hope, as arithmetic and other operations are implemented using logic gates, there must be some syntactic way to recognize it.

It seems insane, but the idea is to build up other types using the basic bit type. 

## Lisp-like Macro System

I'm inspired by metaprogramming to create an ability to expand the syntax, which explains why there's only one native type. The user is allowed to define new aspects of the grammar, and employ new operations. 

A problem would be representing the differences between operations and data. In lisp, it's fairly easy since it's positional. I dislike lisp's syntax, however, because it's a bit counter intuitive and prefer a more natural syntax. Python probably has the most intuitive syntax, but personally C itself is fairly easy to read because it's terse.

```
int x = 42;
int y = x + 42;

let int x equal 42
let int y equal x + 42
```

I can go like javascript and lisp and just have an `eval` type statement that represents the code, and provide a way to represent it differently, but I'm unsure of how it'd work. My gripe is the syntax of it. Let's break it down a bit more.

You'd have to have the ability to modify the automaton, essentially. 

But it should be fairly simple, when you think of it. If we go to C syntax, every line is essentially a statement.

so

```
int x = 42; // is a statement
```

Lets say we create a construct which defines the grammar for a statement. So lets say I want an operator which adds all following values together.

```
macro: 
type var [:=] value ...; { 
	var = value + ...;
}
```

Which means that `int_8 x := 34 14 15 19;`. In the definition `type` is the signifier for the type variable, so the user can lay down what type they have, the var represents the symbol of the varable. `[:=]` defines the operator's symbols, and `value` is just the name for the base type, which I guess can be inherited by other types? The definition follows on previous syntactical rules and `...` is just the construct for rolling out something I guess.

Let me make an addition statement as well.

```
macro:
(var op[+] var) {
	...bitwise operation for it
}	
```

I guess this is an enclosed expression, so it can be embedded into statements (`x = y + z`). I guess it goes on a right to left operand as well. How does it evaluate brackets? Bracket notation will just have to be meta, so it will always evaluate that expression first.

I'll want to go into syntax a bit on this for sure. It's clear some form of regular expression is used to define it. To make something evaluable at runtime: 

## Concurrency & Temporal Logic

Serial programming is archaic, and I want to create a language that is more interesting than a -> b -> c.

My experience with concurrent programming isn't multi-threaded. It's javascript async functions, so I probably want to go exploring threads before I do anything, but perhaps my ignorance on the topic will give me more interesting ideas so I'll seek to exploit that when I can. 

JS async functions are fun to use, but they're not multi-threaded proper, and you can't manipulate the ins and outs of em much. 

I thought to use a different theory [I wrote]() with regards to plot-lines in literary analysis. It's hard to explain fully, but as a person reads a book, they construct multiple plotlines which are (in the theory) observed from the different entities within the story. Entities includes anything, from inanimate objects (Ring of Power) to characters (Bilbo). 

It's technically single processed, as it's a single reader processing the book, but if we can add multiple books in the same *world*, which allow multiple readers to each interact and construct the world individually. These readers can then communicate with one another what happens, but that's where the analogy dies.

My idea is to have scopes (think set theory, or boxes) where entities in those scopes are limited to those scopes, both outside, from an internal scope. Entities can exit or enter a scope. They all exist inside a general scope.

The beautiful thing about it is the interactions between scopes. Scopes have a series of instructions that they run through. I should probably write what I mean right now to make things make sense.

~~~
int x = 5;  

scope A (int count) { // define the scope or function really  
	while (p < count) {
		int p = 0;
		point pt_1;
	}
	
	if (p < x) wait; // error, because x doesn't exist, even when nested

	if (p == 4) wait;
	
	die; // default if unspecified, kills the scope after it finishes executing
}

A(x); // execute scope

operation add -> A {  // define operation in A's context, p is kept 
	int p = (int p);
	if (p < 5) p++;
	wait;
}

send add and execute; // sends and executes right away. If the scope is in the middle of the while loop, then it will execute then.
	// if it can't find anything (i.e. it can't find p's definition) then it returns an error. 
send add at pt_1; // sends the operation at pt_1 and executes, if it finds it;
send add and wait for wait; // sends and waits for a wait. When it gets to the wait, it executes.
send add and wait for definition; // sends and if any anything is undefined, then it waits until it is defined.

~~~

It seems bad coding practice to be able to reference and modify things inside the scope, but my purpose is to make a natural and interesting language, not a clean language. The idea is that you send someone into a room, and they do things for you while you handle your own stuff. You should know what's in the room before you send someone to modify the stuff inside it.

When the scope dies, it's released from memory and no longer persists.

Can we expand this?

What if we have things that connect between rooms? Like a light switch in one room, and a light bulb in another. Thus, it involves shared state.

This is very similar to the actor model of concurrency, but in a more meta-programming type of way, since we're literally modifying the instructions. We also have the idea of rooms rather than only actors, where actors can go into a room, do stuff within the room, leave. The issue is that actors can't usually persist outside their room, which me be something we want to do. So we can send an object somewhere, with a script of action?

I think one way to solve the differences in scope is the have a sort of interface between rooms. But at what point am I just recreating objects? The interface would rather be something like entering a scope. To see how far I can go modifying a scope, I'll want to see what threads can really do.

### Temporal Logic

The issue with coding temporal logic in compsci is reliability, even if going off the computer's dimension of time (clock cycles).

Time would have to be simulated by the language itself.

### Having Fun with This

```
while (true) {
	scope A (void) {
		while (true) {
			;
		}
	}
	A();
}
```

This prints out an endless number of persistent scopes. 

## Objects & Ontology

Objects are a very metaphysical (if not semantic) construct, which I think added to their popularity. It's a natural way of thinking, seeing something smaller, and building it up. So why haven't objects really leant themselves to artificial intelligence? 

## Probability & Modality

Probability is always an interesting 

## Self-Modifying

I want to add the ability to self-modify. 

It'd have to be additive rather than truly self-modifying. i.e. when a new definition is made, it creates new instructions in memory and apply the variable to it rather than rewrite the current ones.

## Graph Inspired Constructions?

Graphs have always seemed to be the most intuitive. 

## Ontology and Merology

Merology is the study of parts and wholes.
