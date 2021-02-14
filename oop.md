## OOP cheatsheet

##### OOP: Object oriented programming is programming paradigm whrere everything is represented as an object

##### Class: A class is a template or blueprint form which objects are created.

#### OOP Principals:
Threre are 4 of them.
1. Encapsulation:
2. Inheritance
3. Polymorphism
4. Abstraction


#### Encapsulation:

- Process of wrapping data and methods together into a single unit.
- It is a technique that helps keep instance variable protected. This can achieved by using 'private' access modifiers that can't be accessed by anytime outside the class

##### Advantages:
- Can make a class read-only or write only.
- Control over the data.
- Data Hiding


#### Inheritance:

- Inheritance is a mechanism in which one object acquires all the states and behaviors of a parent object

In Java we can inherite,
1. Public instance methods
2. Private instance variables (through public getter and setter method.)

There are 5 type of inheritance.
1. Single
2. Multilabel
3. Hierarchical
4. Multiple
5. Hybrid

**NB: Multiple and Hybrid inheritance in java can be implement usning `Interface`**
##### Advantages:
- Resuable code
- More flexibility to change the code

#### Polymorphism:
Polymorphism means 'a state of having many shapes'.

Polymorphisms are two types:
1. Compile time (Static binding)
2. Runtime (Dynamic binding)

Compile time polymorphisms can be achieve trough `method overloading` whrere runtime can achieve through `mehtod overrinding`.

Mehtod overloading: If a class method has multiple methods that have same name but different parameters or return type, this is named method overloading 

Method overriding: If subclass has the same method as declared in the superclass , this is known as method overriding.
#### Abstraction:

Abstraction is a process of hiding the implementation details and showing only functionality to the user.

Abstract class:
- An abstract class is one that contains the keyword `abstract`.
- Abstract classes can't be instantiate.
- They can have constructors, static mehods, and final methods.

Abstract methods:
- An abstract mehod is one that contains the keyword `abstract`.
- Abstract mehdod dosen't have implementation (method body).
- They shouldn't be marked as `private`.

Abstract class and Abstract methods:
- If at least one abstract method exist in a class then the whole class should be abstarct.
- Can have abstract class with no abstract methods.
  
##### When to mark a class as abstract?
- To force sub classes to implement abstract methods.
- To stop having actual objects of that class
- To keep having class reference
- To retain common class code.