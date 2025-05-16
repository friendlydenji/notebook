* Identify the aspects of your application that vary and seperate them from what stays the same.
* Program to interface, not an implementation.
* Favor composition over inheritance.

**The Strategy Pattern** defines a family of algorithms, encapsulates each one, and makes them interchangeable, **Strategy** let the algorithms vary independently from the client that use it.

**The Observer Pattern** defines a one-to-many dependency between objects so that when one object change state, all of its dependency are notified and updated automatically.

* Strive for loosely coupled designs between objects that interact
* Class should opened for extension, but closed for modification.

**The Decorator Pattern** attaches additional responsibilities to an object dynamically. **Decorators** provide a flexible alternative to subclassing for extending functionality.

**The Factory Method Patter** defines an interface for creating an object, but less subclasses decide which class to instantiate. **Factory Method** lets a class defer instantiation to subclasses.

* Depend upon abstractions. Do not depend upon concrete class.

**The Abstract Factory** Pattern provides an interface for creating family of related or dependent objects without specify their concrete class.

**The Singleton Pattern** assures a class has only on instance, and provides a global point of access to it.

**The Command Pattern** encapsulates a request as an object, thereby letting you parameterize other objects with diffirent requests, queue or log requests, and support undoable operations.

**The Adaptor Pattern** converts the interface of a class into another interface the client expect. **Adaptor** lets classes work together that couldn't otherwise because of incompatible interfaces.

**The Facade Pattern** provides a unified interface to a set of interfaces in a subsystem. **Facade** defines a higher-level interface that makes subsystem easier to use.

* Talk only to your immediate friend.

**The Template Method** Pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses. **Template Method** lets subclasses redefine certain steps of an algorithm without changing the algorithm's structure.

* Don't call us, we'll call you.

**The Iterator Pattern** provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation.

* A class should have only one reason to change.

**The Composite Pattern** allows you to compose objects into tree structures to represent part-whole hierachies. **Composite** lets clients treat individual objects and compositions of objects uniformly.

**The State Pattern** allows an object to alter its behavior when its internal state change. The object will appear to change its class.

**The Proxy Pattern** provides a surrogate or placeholder for another object to control access to it.