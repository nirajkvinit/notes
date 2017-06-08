
=== strict equality operator

--- Variable should always be declared with the keyword var. If a variable is declared without var keyword then the variable will become part of the global scope.

--- Within a function always declare variable always at the top.

-------------------------------------------------------------------------------------------------------------------------------------

http://tutorialzine.com/2015/12/the-languages-and-frameworks-you-should-learn-in-2016/



In JavaScript, however, when you define multiple functions with the same name, the one that appears last in your code wins.

The in operator looks for a property with a given name in a specific object and returns true if it finds it.

Enter the hasOwnProperty() method, which is present on all objects and returns true only if the given property exists and is an own property.

By default, all properties that you add to an object are enumerable, which means that you can iterate over them using a for-in loop. The for-in loop enumerates all enumerable properties on an object, assigning the property name to a variable.

If you just need a list of an object’s properties to use later in your program, ECMAScript 5 introduced the Object.keys() method to retrieve an array of enumerable property names.

There are two different types of properties: data properties and accessor properties. Accessor properties don’t contain a value but instead define a function to call when the property is read (called a getter), and a function to call when the property is written to (called a setter).

It helps to think of JavaScript objects as hash maps where properties are just key/value pairs. You access object properties using either dot notation or bracket notation with a string identifier. You can add a property at any time by assigning a value to it, and you can remove a property at any time with the delete operator. You can always check whether a property exists by using the in operator on a property name and object. If the property in question is an own property, you could also use ­ hasOwnProperty() , which exists on every object. All object properties are enumerable by default, which means that they will appear in a for-in loop or be retrieved by Object.keys() .

There are two types of properties: data properties and accessor properties. Data properties are placeholders for values, and you can read from and write to them. When a data property holds a function value, the property is considered a method of the object. Unlike data properties, accessor properties don’t store values on their own; they use a combination of getters and setters to perform specific actions. You can create both data properties and accessor properties directly using object literal notation.

Constructors are just normal functions that are called with the new oper­ator. You can define your own constructors anytime you want to create multiple objects with the same properties. You can identify objects created from constructors using instanceof or by accessing their constructor property directly.

Every function has a prototype property that defines any properties shared by objects created with a particular constructor. Shared methods and primitive value properties are typically defined on prototypes, while all other properties are defined within the constructor. The constructor property is actually defined on the prototype because it is shared among object instances.

The prototype of an object is stored internally in the [[Prototype]] property. This property is a reference, not a copy. If you change the proto­type at any point in time, those changes will occur on all instances because of the way JavaScript looks up properties. When you try to access a property on an object, that object is searched for any own property with the name you specify. If an own property is not found, the prototype is searched. This searching mechanism means the prototype can continue to change, and object instances referencing that prototype will reflect those changes immediately.

JavaScript supports inheritance through prototype chaining. A prototype chain is created between objects when the [[Prototype]] of one object is set equal to another. All generic objects automatically inherit from Object .prototype . If you want to create an object that inherits from something else, you can use Object.create() to specify the value of [[Prototype]] for a new object.

You accomplish inheritance between custom types by creating a proto­type chain on the constructor. By setting the constructor’s prototype property to another value, you create inheritance between instances of the custom type and the prototype of that other value. All instances of that constructor share the same proto­type, so they all inherit from the same object. This technique works very well for inheriting methods from other objects, but you cannot inherit own properties using prototypes.

To inherit own properties correctly, you can use constructor stealing, which is simply calling a constructor function using call() or apply() so that any initialization is done on the subtype object. Combining constructor stealing and prototype chaining is the most common way to achieve inheritance between custom types in JavaScript. This combination is frequently called pseudo­classical inheritance because of its similarity to inheritance in class-based languages.

