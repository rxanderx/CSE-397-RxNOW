# White paper: Design Patterns

## Title: Comparative Analysis of Factory, Singleton, Facade, and Adapter Patterns
**Name:** Kelson Gneiting
**Course/Semester/Section**: CSE 397 Professional Career Projects: Summer 2026: Section 31
**Instructor**: Brother Clements
**Date**: 2026-06-20

## Summary: 
This whitepaper compares four widely used design patterns: Factory, Singleton, Facade, and Adapter. Each pattern solves a different kind of software design problem, but they all aim to improve code reuse, flexibility, and maintainability. The paper focuses on when each pattern is appropriate, what tradeoffs it introduces, and how it supports larger software systems.

## Introduction: 
The purpose of this paper is to compare four key design patterns—Factory, Singleton, Facade, and Adapter—that appear frequently in object-oriented software development and modern application architecture. I researched general design-pattern guidance, a scholarly review on design-pattern quality and detection, a software engineering video about pattern literacy, and practical reference material about each pattern. These patterns matter because they help developers structure code so it is easier to maintain, easier to test, and easier to extend as a system grows.

Design patterns are reusable solutions to commonly occurring problems in software design. They are not rigid structures to copy directly into source code, but rather descriptions and templates for solving particular types of problems in various contexts and programming languages. The patterns discussed here are especially useful in the kind of layered systems used in class projects. Factory helps control object creation, Singleton enforces one shared instance, Facade simplifies access to complex subsystems, and Adapter bridges incompatible interfaces.

### Historical Context
Design patterns originated as an architectural concept by Christopher Alexander as early as 1977 in his work *A Pattern Language*. The concept was adapted to software by Kent Beck and Ward Cunningham in 1987, who presented their findings on pattern languages at the OOPSLA conference. However, design patterns gained widespread popularity in computer science after the publication of *Design Patterns: Elements of Reusable Object-Oriented Software* in 1994 by the "Gang of Four" (Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides). This foundational book categorized twenty-three design patterns into three primary groups: creational, structural, and behavioral. Together, these patterns show that design pattern application is less about memorizing names and more about recognizing recurring engineering problems and applying proven solutions.

## Overview: 
### Factory
The Factory pattern is a creational pattern that uses a central object or method to create instances of different classes based on specific conditions or parameters. Its purpose is to centralize object creation so client code does not need to know the exact class being instantiated. This is useful when the software may need to create different objects based on user input, configuration, or runtime conditions.

### Singleton
The Singleton pattern is a creational pattern that restricts a class to have only one instance while providing a global point of access to that instance. Singleton is also a creational pattern, but it has a narrower purpose: ensuring that only one instance of a class exists in the application. It is often used for shared services such as logging, configuration, or shared resource managers. Although simple in concept, Singleton is controversial because it can introduce hidden global state and make tests harder to isolate.

### Facade
The Facade pattern is a structural pattern that provides a single, simplified interface to a complex subsystem of classes, components, or services. Facade is a structural pattern that provides a simpler interface to a larger subsystem. Instead of exposing every internal class directly, it gives the rest of the system one easy entry point. This makes code easier to read and reduces coupling between components.

### Adapter
The Adapter pattern is a structural pattern that converts the interface of a class into another interface that clients expect, allowing incompatible interfaces to work together. Adapter is another structural pattern, but its purpose is translation rather than simplification. It lets two incompatible interfaces work together by wrapping one interface and exposing another one that the client expects. This is especially useful when integrating with old code, third-party libraries, or systems that cannot be rewritten.

## Strength and Weakness: 
### Factory
Strengths: Factory improves code reuse, hides object creation details, and keeps client code flexible. It is especially good when the exact object type may change later.

Weaknesses: It can add extra layers of indirection and may feel unnecessary for small programs. If overused, it can make simple object creation harder to follow.

### Singleton
Strengths: Singleton gives a single shared access point, which can be useful for shared services or application-wide configuration. It is easy to understand at first glance.

Weaknesses: Singleton can behave like disguised global state. That makes testing, concurrency, and dependency management more difficult if it is not used carefully.

### Facade
Strengths: Facade reduces complexity by hiding subsystem details and gives developers a cleaner API. It improves readability and lowers coupling between layers.

Weaknesses: A Facade can become too large if it tries to do too much. If it grows into a catch-all class, it stops being a simplifier and becomes another source of complexity.

### Adapter
Strengths: Adapter is excellent for integrating code that cannot easily be changed. It lets teams reuse existing systems instead of rewriting them.

Weaknesses: Too many adapters can create a maintenance burden, and poorly designed adapters may hide interface problems instead of solving them.

# Useage and Applicability: 
* **Factory** is used when the application needs to decide at runtime which class to create. It is common in GUI frameworks, dependency injection setups, and any system that produces different objects from the same request.
* **Singleton** is used when only one shared instance should exist, such as a configuration manager, cache coordinator, or logging service. It is best when shared state truly needs to be centralized.
* **Facade** is used when a subsystem is too complex for the rest of the application to interact with directly. It is helpful when there are multiple lower-level services that should be hidden behind one cleaner interface.
* **Adapter** is used when two systems or classes need to work together but their interfaces do not match. It is common in integration work, legacy modernization, and API wrapping.

These patterns are most useful when the project is large enough that direct coupling would create maintenance problems. In small projects, simple code may be better than introducing a pattern too early.

# Comparison: 
Factory and Singleton both deal with object creation, but they solve different problems. Factory chooses which object to create, while Singleton restricts how many instances exist. In practice, Factory is usually the more flexible choice.

Facade and Adapter both simplify interaction with other code, but they do so in different ways. Facade makes a complex subsystem easier to use, while Adapter makes an incompatible interface usable. Facade reduces complexity; Adapter resolves mismatch.

Alternative approaches exist for all four patterns. Factory can sometimes be replaced by direct construction or dependency injection. Singleton can often be replaced with dependency injection and controlled object lifetimes. Facade can be replaced with smaller service classes or clean API boundaries. Adapter can sometimes be replaced by interface refactoring, wrapper classes, or data mapping functions.

# Additional Design Patterns
While this whitepaper focuses on Factory, Singleton, Facade, and Adapter, the broader design pattern landscape includes many more patterns organized into different categories:

## Other Creational Patterns
Beyond Factory and Singleton, other creational patterns include:
- **Abstract Factory**: Provides an interface for creating families of related objects without specifying their concrete classes.
- **Builder**: Separates the construction of complex objects from their representation, allowing flexible object creation.
- **Prototype**: Creates new objects by copying a prototypical instance rather than creating from scratch.
- **Dependency Injection**: Allows a class to accept the objects it requires from an injector instead of creating them directly.

## Other Structural Patterns
Beyond Facade and Adapter, important structural patterns include:
- **Bridge**: Decouples an abstraction from its implementation so the two can vary independently.
- **Composite**: Composes objects into tree structures to represent part-whole hierarchies.
- **Decorator**: Attaches additional responsibilities to an object dynamically, providing a flexible alternative to subclassing.
- **Proxy**: Provides a surrogate or placeholder for another object to control access to it.

## Behavioral Patterns
Behavioral patterns address how objects collaborate and communicate:
- **Observer (Publish/Subscribe)**: Defines a one-to-many dependency where state changes in one object result in all dependents being notified automatically.
- **Strategy**: Defines a family of algorithms, encapsulates each one, and makes them interchangeable.
- **Command**: Encapsulates a request as an object, allowing parameterization of clients with different requests.
- **State**: Allows an object to alter its behavior when its internal state changes.
- **Template Method**: Defines the skeleton of an algorithm in an operation, deferring specific steps to subclasses.
- **Chain of Responsibility**: Passes requests along a chain of handlers, giving each handler the opportunity to process or pass the request.

## Concurrency Patterns
For multithreaded applications, concurrency patterns provide solutions for thread management and synchronization:
- **Active Object**: Decouples method execution from method invocation using asynchronous processing.
- **Thread Pool**: Creates a number of threads to perform queued tasks efficiently.
- **Monitor Object**: Protects shared data by ensuring methods are subject to mutual exclusion.
- **Double-Checked Locking**: Reduces synchronization overhead by testing a condition before acquiring a lock.

# Summary: 
My recommendation is to use Factory, Facade, and Adapter more often than Singleton in modern software design. Factory and Facade generally improve maintainability without creating as much hidden state, and Adapter is a practical choice for integrating systems. Singleton should be used sparingly and only when a single shared instance is genuinely required.

The biggest lesson from comparing these patterns—and understanding the broader pattern landscape—is that design patterns are tools, not rules. A good developer chooses the smallest pattern that solves the actual problem and recognizes that multiple patterns exist for different contexts. The Gang of Four's twenty-three patterns have been expanded over decades to address specific domains like web design, user interfaces, security, and concurrent programming. When applied intentionally and in combination with modern practices like dependency injection and clean architecture principles, these patterns make software easier to change, explain, and maintain.

Design patterns accelerate development by providing proven paradigms that prevent common mistakes and enhance code readability for those familiar with them. However, inappropriate use of patterns can unnecessarily increase complexity. The key is understanding not only when to apply patterns but also when to avoid them in favor of simpler, more direct solutions.

# References:
>You need to use more than 5 different sources: 
    1. LLM: i.e. ChatGPT, Gemini, Deepseek, Co-pilot
    2. Wiki: i.e. Wikipedia, etc
    3. Video: i.e. YouTube, Udemy, LinkedIn
    4. Scholarly paper (primary source): Google scholar, BYU Libary
    5. Website

1. OpenAI ChatGPT, generated analysis support for this whitepaper, 2026.
2. Wikipedia contributors, “Design pattern,” Wikipedia, the free encyclopedia. https://en.wikipedia.org/wiki/Design_pattern
3. Stackify, “Introduction to Design Patterns in Software Development.” https://stackify.com/introduction-to-design-patterns-in-software-development/
4. YouTube, “The Truth About Design Patterns NO ONE Tells You (They’re Not Optional).” https://www.youtube.com/watch?v=Ayb1whga5JE
5. Kesavan, Elavarasi. “The Evolution of Software Design Patterns: An In-Depth Review.” International Journal of Innovations in Science Engineering and Management, 2025. https://ijisem.com/journal/index.php/ijisem/article/view/249/227 (found on google scholar)
6. Refactoring.Guru, “Design Patterns.” https://refactoring.guru/design-patterns
