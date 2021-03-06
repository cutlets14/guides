# Chapter 1
## The Problem Design Solves
- It is imperative that one views the world as a series of spontaneous interactions between objects. OOD requires that you shift from thinking of the world as a collection of predefined procedures to modeling the world as a series of messages that pass between objects.
- Failures of OOD may look like failures of coding technique but they are often failures of perspective. Immerse yourself in the world of objects and the rest will flow naturally.
  
## A Practical Definition of Design
- Practical design does not anticipate what will happen to your application, it merely accepts that something will and that, in the present, you cannot know what.
- It doesn't guess the future; it preserves your options for accommodating the future.
- It doesn't choose; it leaves you room to move.
- The purpose of design is to allow you to design later and its primary goal is to reduce the cost of change.

## Design Principles
- Design is not the act of following a fixed set of rules, it's a journey along a branching path wherein earlier choices close off some options and open access to others.
- The tools of OOD are principles and patterns. Following them will improve your code.
- SOLID acronym - Single Responsibility, Open-Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion.
- DRY - Don't Repeat Yourself.

### Design Patterns
- As described in "Design Patterns", patterns are simple and elegant solutions to specific problems in object-oriented software design that you can use to make your own designs more flexible, modular, reusable, and understandable.
- Patterns and principles are still merely tools and require careful application fostered through experience to build beautiful things.
- BUFD = Big Up Front Design; completely specifying and totally documenting the anticipated future inner workings of all of the features of the proposed application.
- OOD = arranging what code you have so that it will be easy to change. The primary goal, as stated before, of design is to reduce the cost of change.

## Judging Design
- OOD metrics cannot identify designs that  do the wrong thing in the right way.
- The ultimate software metric would be cost per feature over the time interval that matters, but this is not easy to measure. Cost, feature, and time are individually difficult to define, track, and measure.
- If lack of a feature will force you out of business today it doesn't matter how much it will cost to deal with the code tomorrow; you must do the best you can in the time you have. Making this kind of design compromise is like borrowing time from the future and is known as taking on technical debt.
- This is a loan that will eventually need to be repaid, quite likely with interest.

The goal is to write software with the lowest cost per feature (i.e., well-designed so future changes cost little).

# Chapter 2
## Designing Classes with a Single Responsibility
- Your goal is to model your application, using classes, such that it does what it is supposed to do right now and is also easy to change later
- Your application needs to work right now just once; it must be easy to change forever.
- The code that one writes must be TRUE - Transparent, Reasonable, Usable, Exemplary
  - Transparent - The consequences of change should be obvious in the code that is changing and in distant code that relies upon it
  - Reasonable - The cost of any change should be proportional to the benefits the change achieves
  - Usable - Existing code should be usable in new and unexpected contexts
  - Exemplary - The code itself should encourage those who change it to perpetuate
  these qualities
- Looking for nouns that represent objects in the domain is a good way to identify potential classes. This, alone, isn't enough - you will need to ensure that a noun has both data and behavior associated with it to qualify as a class.

## Determining if a class has a single responsibility
1. Pretend that the class is sentient and interrogate it.
2. Describe the class in a single sentence.
   1. If the sentence contains "and", the class likely has more than one responsibility.
   2. If the sentence contains "or", the class has more than one responsibility and they aren't even very related.
3. When everything in a class is related to its central purpose, the class is said to be highly-cohesive or to have a single responsibility. Said differently, the class is cohesive when everything the class does is highly related to its purpose.

## When to make the decision?
- When the future cost of doing nothing is the same as the current cost, postpone the decision. Make the decision only when you must with the information you have at the time.

## Writing code that embraces change
1. Depend on behavior, not data.
   1. Follow D.R.Y. - every tiny bit of behavior lives in one and only one place.
   2. Hide instance variables - always hide instance variables by wrapping them in accessor methods instead of directly referring to them even from the class that defines them. Use `attr_reader` as a quick way to create wrapping/encapsulating methods for instance variables.
   3. Hide data structures - never depend on a complex data structure and try your best to avoid leaky references. References to data structures are not DRY and such knowledge should be limited to one place. Use the Ruby `Struct` class to wrap a structure which trades indexing into a structure for sending messages to an object. Usage of `Structs` allows one to isolate messy structural information and DRYs out the code making the class far more tolerant of change. At all times, try to hide the mess even from yourself.
2. Enforce Single Responsibility everywhere
   1. Extract extra responsibilities from methods - Methods, like classes, should have a single responsibility - for all of the same reasons. ** You do not have to know where you're going to use good design practices to get there. Good practices reveeal design.**
   2. Methods that have a single responsibility confer the following benefits:
      1. Expose previously hidden qualities - Refactoring a class so that all of its methods have an SR has a clarifying effect on the class - even if you do not intend to reorganize the methods into other classes today.
      2. Avoid the need for comments - if a bit of code inside a method needs a comment, extract that bit into a separate method. The new method name serves the same purpose as did the old comment.
      3. Encourage reuse - other programmers will reuse the methods instead of duplicating the code. They will follow the pattern you have established and create small, reusable methods in turn.
      4. Are easy to move to another class - small methods are easy to move because rearrangement is much easier without the need for a lot of method extraction and refactoring.
   3. Isolate extra responsibilities in Classes - preserve your ability to make a decision later
      1. Use the same pattern as hiding data structures by leveraging a `Struct` with a `do/end` block enclosing the method of interest.
      2. If you have a muddled class with too many responsibilities, separate those responsibility into different classes. Concentrate on the primary class.
      3. If you cannot remove extraneous responsibilities, isolate them and ensure that they don't leak into the class. Isolating them allows them to be extracted easily if the domain is clarified in the future.
  



