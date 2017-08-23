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
