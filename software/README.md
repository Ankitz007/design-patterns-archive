# Software Design Patterns

This folder contains flash cards for various design patterns, including the Gang of Four (GoF) patterns and other common design patterns. The flashcards are designed to help you learn and understand these patterns in a quick and efficient manner.

## Contents

So far, the following design patterns have been included:

- **Creational Patterns:** Design patterns that deal with object creation mechanisms, trying to create objects in a manner suitable to the situation.
  - [Singleton](creational/singleton/README.md): A creational design pattern that ensures a class has only one instance and provides a global point of access to it.
  - [Factory Method](creational/factory-method/README.md): A creational design pattern that defines an interface for creating an object, but lets subclasses alter the type of objects that will be created.
  - [Abstract Factory](creational/abstract-factory/README.md): A creational design pattern that provides an interface for creating families of related or dependent objects without specifying their concrete classes.
  - [Builder](creational/builder/README.md): A creational design pattern that allows the creation of complex objects step by step.
  - [Prototype](creational/prototype/README.md): A creational design pattern that allows cloning of objects, even if the concrete classes are unknown at runtime.

- **Structural Patterns:** Design patterns that deal with object composition or structure.
  - [Adapter](structural/adapter/README.md): A structural design pattern that allows objects with incompatible interfaces to work together.
  - [Decorator](structural/decorator/README.md): A structural design pattern that allows behavior to be added to individual objects, either statically or dynamically, without affecting the behavior of other objects from the same class.
  - [Facade](structural/facade/README.md): A structural design pattern that provides a simplified interface to a complex subsystem.
  - [Proxy](structural/proxy/README.md): A structural design pattern that provides a surrogate or placeholder for another object to control access to it.
  - [Composite](structural/composite/README.md): A structural design pattern that allows you to compose objects into tree structures to represent part-whole hierarchies.
  
- **Behavioral Patterns:** Design patterns that are concerned with algorithms and the assignment of responsibilities between objects.
  - [State](behavioral/state/README.md): A behavioral design pattern that allows an object to change its behavior when its internal state changes.
  - [Strategy](behavioral/strategy/README.md): A behavioral design pattern that enables selecting an algorithm's behavior at runtime.
  - [Observer](behavioral/observer/README.md): A behavioral design pattern that defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
  - [Command](behavioral/command/README.md): A behavioral design pattern that turns a request into a stand-alone object containing all information about the request.
  - [Iterator](behavioral/iterator/README.md): A behavioral design pattern that provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation.
  - [Template Method](behavioral/template/README.md): A behavioral design pattern that defines the skeleton of an algorithm in a method, deferring some steps to subclasses.

## References

- [Gang of Four Design Patterns](https://en.wikipedia.org/wiki/Design_Patterns)
- [Design Patterns](https://refactoring.guru/design-patterns)
