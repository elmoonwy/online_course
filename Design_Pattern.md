# Design Pattern
## The Strategy Pattern

You should identify the same and vary behavior.
Put shared behavior into base class, put vary behavior into interface.

> You can combine composition and inheritance together, using composition for the behaviors that need more flexibility. And inheritance for behavior that you know won’t need to change.  

What is **Strategy Pattern**?
It defines a family of algorithms, encapsulate each one, and makes them interchangeable, Strategy lets the algorithm vary **independently** from clients that use it.

> Design Principle #1  
> Encapsulate what varies  
> Design Principle #2  
> Favor composition over inheritance.  
> Design Principle #3  
> Program to an interface  

## The Observer Pattern

> The **Observer Pattern** define a one to many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.  

What different between push and pull notification?

The order of observer doesn’t matter.
The goal of observer pattern is reduce dependency between the subject and the object.

> Design Principle #4  
> Strive for loosely coupled designs between objects that interact  

## The Decorator Pattern

> Design Principle #5  
> Classes should be open for extension but closed for modification  

> The **Decorator Pattern** attaches additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.  

There are 3 ways to modify behavior.
1. `override` totally change parent’s behavior, but it require inheritance
2. `composition` over `override` , flexible change the behavior, even in run time
3. decorator pattern

If i want to change object behavior, which one I should use? strategy pattern or decorator pattern?

The decorator pattern give a object possibility to have multiple variety in runtime. The strategy pattern make your object more flexible and response to behavior change.

## The Singleton Pattern

> **Singleton Pattern** ensures a class has only one instance, and provides a global access point to it.  

How swift implemented a lazy `Singleton Pattern` in swift?
1. `static` annotation


How to handle multiple thread in lazy `Singleton Pattern`? 
1. Use eagerly init
2. Use `lock`

## The State Pattern

> **The State Pattern** allows an object to alter its behavior when its internal state changes. The object will appear to change its class.  

You should think about **State Pattern** when you saw lots of `if-else`.

The **state pattern** abstract each state into a state object, so that state object only need to focus on it own state and it doesn’t need to know any other state.

Let say that again!
1. Encapsulate what varies
2. Favor composition over inheritance
3. Keep a class closed for modification but open for extension

What is the different between **state pattern** and **strategy pattern**?
We are really providing the behavior of an object by composing it at runtime with one of a family of algorithm. With state, we are often continually changing the behavior of an object by setting its behavior via state machine.

## The Collection Pattern

> **The Iterator Pattern** provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation.  

> Design Principle #6  
> A class should have only one reason to change. aka. Single responsibility principle  

Every object can has responsibility. But responsibility may change in the future. So the more responsibility a object have, the more change you have to change it. Thus, we should try our best to keep 1 object has only 1 responsibility.

## Factories Pattern

> **The Factory Method Pattern** defines an interface for creating an object, but lets subclass decide which class to instantiate. Factory Method lets a class defer instantiation to subclass.  

You may want to initialize a instance base on condition. But you will run into a large `switch` if you have lots of condition. In order to repeat the long `switch` everywhere, you could put them into a single class. So only the class know all dirty work.
