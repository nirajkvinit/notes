* Reading an unknown property always returns undefined .
* Primitive values are always immutable. Properties can’t be changed, added, or removed.
* All nonprimitive values are objects.
* Like all primitives, strings are immutable; you need to create a new string if you want to change an existing one.
* You can declare and initialize several variables with a single var statement. However, the recommendation is using one statement per variable.
* Because of hoisting, it is usually best to declare variables at the beginning of a function.
* Each variable declaration is hoisted: the declaration is moved to the beginning of the function, but assignments that it makes stay put.
* IIFE (immediately invoked function expression, pronounced “iffy”). An IIFE is a function expression that is called immediately after you define it.
* You can spread a string over multiple lines by escaping the end of the line (the line-terminating character, the line terminator) with a backslash:
#Undefined
	* undefined means “no value.” Uninitialized variables are undefined
	* Missing parameters are undefined.
	* If you read a nonexistent property, you get undefined.

#null
	* null means “no object.” It is used as a nonvalue whenever an object is expected

#Checking for undefined or null
	```if (x === undefined || x === null) {
		...
	}```

	* You can also exploit the fact that both undefined and null are considered false :
	```if (!x) {
		...
	}```

* typeof is mainly used for primitive values, while instanceof is used for objects.

#Equality Operators
JavaScript has two kinds of equality:
• Normal, or “lenient,” (in)equality: == and !=
• Strict (in)equality: === and !==
Normal equality considers (too) many values to be equal, which can hide bugs. Therefore, always using strict equality is recommended.

#Closures
* Each function stays connected to the variables of the functions that surround it, even after it leaves the scope in which it was created.
* A closure is a function plus the connection to the variables of its surrounding scopes.


