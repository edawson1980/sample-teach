# sample-teach
short lesson on prototypes in JavaScript

## Objectives
*by the end of this lesson, students should be able to:*
- Demonstrate a use case of prototypal inheritance
- Explain how inheritance makes things easier for programmers
- Write a custom constructor that gives an example of prototypal inheritance
- Properly use namespacing to keep code organized

## Preparation 
*before this lesson, students should already have a grasp on:*
- Basic JavaScript
- Functions in JavaScript
- OOP (object-oriented programming)

## Prototypes in JavaScript (5 minutes)

**What are prototypes?**

**Prototypes** are the *idea* of an object.  They are the original version of an object, from which all other versions of that particular object are copied.  *All objects in JavaScript are automatically created with the property **prototype**, even if we don't use it.*
  
  For Example:
  ``` 
  function Person (first, last, age, eyecolor){
    // some code here
  }
  ```
**Person** is an object, with various properties assigned to it.  **Person** is **also** its own *prototype*...the idea of Person, and everything associated with it, exists in the ether - even if we have not created a tangible Person yet.

So how do we create a Person?  With **constructors**.

## Constructors (5 minutes)

When we create a use case of an Object, we use something called a Constructor.  Constructors are used to create *instances* of objects (actual occurrences of the object).  In order to use a Constructor, we have to become familiar with another high-level idea...the idea of *this*.

*This* does exactly what it seems like it might...it denotes or points to which exact Object instance we are referring to.
Take this example:
```
  function Person (first, last){
    this.firstName = first,
    this.lastName = last
   }
 ```
 what **this(dot)something** means is "in *this specific instance* of Person, and only in this specific instance of Person, does some particular condition/rule/property/etc apply".
 
 now that we've got a grasp on **this**, let's use a Constructor to create a Person.
 
 ```
 function Person (first, last){
  this.firstName = first,
  this.lastName = last
 }
 
 var joe = new Person("Joe", "Biden")
 
 console.log(joe.firstName) // "Joe"
 
 ```
 **this.firstName** (in this case) refers only to the firstName property of the Person Object joe.  If we create another instance of the Person object, and call it Sally,
 ` var sally = new Person("Sally", "Ride") `
 and then we console log 
 `sally.firstName`,
 we get the value `"Sally"`
 
 ## Prototypal Inheritance
 We say that an Object instance *inherits* from its parent object (aka the prototype/ aka there-is-no-spoon).  What we mean is that each time we create a new Object (using the keyword 'new'), that Object immediately and automatically has access to **all of the properties defined in the parent object**.
  In our Person example, this means that every single time we make a new Person, they have access to all of the properties defined in the Constructor (firstName, lastName, eyeColor, etc)...and this is known as Prototypal Inheritance (more commonly referenced as just inheritance).
  Programmers love inheritance, because it keeps our code neat and organized, and because it saves us from having to define all the properties belonging to an Object each time we need to make a new instance.
  
### (A Quick Note about Namespacing)
The basic concept of namespacing as it applies to programming is that we make sure to name all of our variables/functions/objects/etc in such a way that we don't accidentally end up repeating them later in our code.  When we're just starting out this may not seem like a big deal, but as applications grow, it can be very easy to accidentally reuse something.  
The easiest way to think about namespacing is that you've got your code laid out in a hierarchy, like the outline for an essay.
If the top level of your essay is called MY_ESSAY, then everything that follows MY_ESSAY (all the paragraphs, citations, etc) *belong to* MY_ESSAY, and nothing else.  MY_ESSAY is what is known as a *global* object.
The same rules apply with inheritance in JavaScript.  To go back to our Person example:
- Person is the global object
-- and everything inside of Person (and therefore, everything inside of every instance of Person) belongs solely to the Person object
- this is namespacing, and it helps us to keep our code tidy and packaged up.

For a better explanation of namespacing, [read this](https://www.codeproject.com/Articles/829254/JavaScript-Namespace).
  
 
