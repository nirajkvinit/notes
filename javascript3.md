==Data Types==

--Primitive (Value)
----String
----Number
----Boolean
----Undefined
----Null

--Object (Reference)
----Object
----Array
----Function
----Date
----RegExp

console.log((function f(n){return ((n > 1) ? n * f(n-1) : n)})(4)); 24
NaN !== NaN (will be true)

# Questions
* What is `"use strict";` and what does it do?
	Strict Mode is a new feature in ECMAScript 5 that allows you to place a program, or a function, in a "strict" operating context. This 		strict context prevents certain actions from being taken and throws more exceptions. And: ... It catches some common coding bloopers, 		throwing exceptions.

* Does javascript pass parameters by value or by reference?
	
* What is pass by value and what is pass by reference?
	Javascript always passes by value. However, if you pass an object to a function, the "value" is really a reference to that object, so 		the function can modify that object's properties but not cause the variable outside the function to point to some other object

* What are the different types in javascript?
	1. Primitive Value Type
	2. Object Reference Type

* What is the difference between `==` and `===`?
	Strict Equality operator.

* What is the type of NaN and how can we check for it?
	1. NaN type is number
	2. NaN when compared to itself returns false.

* What are the different scopes in javascript?
	Global Scope : Variables are known throughout the application, from the moment they are declared onwards
	Functional Scope : Variables are known within the function they are declared in, from the moment they are declared onwards

* What is variable hoisting?
	This also means that a variable can appear to be used before it's declared. This behavior is called "hoisting", as it appears that the 		variable declaration is moved to the top of the function or global code.

* What is the scope chain?
	Within each execution context is a special object called a scope chain which is used to resolve variables. A scope chain is essentially 	a stack of currently accessible scopes, from the most immediate context to the global context.

* What is an IIFE and why might you use it?
	IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined.
	The primary reason to use an IIFE is to obtain data privacy.
	An IIFE, or Immediately Invoked Function Expression, is a common JavaScript design pattern used by most popular libraries (jQuery, 		Backbone.js, Modernizr, etc) to place all library code inside of a local scope. ... An IIFE protects a module's scope from the 		  	environment in which it is placed.

* What are function closures?
	A closure is an inner function that has access to the outer (enclosing) function's variables—scope chain. The closure has three scope 		chains: it has access to its own scope (variables defined between its curly brackets), it has access to the outer function's variables, 	and it has access to the global variables
	A closure is a record storing a function together with an environment: a mapping associating each free variable of the function 		(variables that are used locally, but defined in an enclosing scope) with the value or reference to which the name was bound 		when the closure was created.

