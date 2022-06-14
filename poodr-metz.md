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
  



