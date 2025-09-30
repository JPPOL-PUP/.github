# PUP team - Way of Code
We follow the SOLID principles to ensure maintainable and robust codebases:

- **Single Responsibility Principle (SRP)**: Each class should have only one reason to change, focusing on a single responsibility.
- **Open/Closed Principle (OCP)**: Software entities should be open for extension but closed for modification.
- **Liskov Substitution Principle (LSP)**: Subclasses must be substitutable for their base classes without affecting program correctness.
- **Interface Segregation Principle (ISP)**: Clients should not be forced to depend on methods they do not use. Prefer multiple, focused interfaces over large, general ones.
- **Dependency Inversion Principle (DIP)**: High-level modules should depend on abstractions, not on concrete implementations. Abstractions should not depend on details; details should depend on abstractions.

The team have agreed on this priority order for the principles:
1. SRP
2. DIP
3. LSP
4. ISP
5. OCP

The reason for the order, is that we now it can be hard to follow all principles at the same time. So this order is for us to tell: If it is a hassle to follow all, then focus on these first.
Questions about SOLID in scala, please talk to the team. And more info on SOLID in React please read here: [link to come]()

## Testing
For testing we use a mix of white box and black box testing. For definition on what white box and black box testing is, see [here]().
- **White Box Testing**: Most of our tests are white box testing, and we want most of our future tests to be white box tests. They help structure our tests, and helps prevent them for becoming too long or inefficient.
- **Black Box Testing**: We use black box testing for external integration tests. Places where we don't own the code, are places where we need to test all scenarios. So all third party libraries, network, packages.

We also have a minimum coverage, that needs to be met before a PR can be merged. // TODO: add place where to read about coverage minimum, and find specs.


## Reviews
It is agreed that a review should be done with our guidelines in mind. What is written here are topics we all have agreed on, and should be followed. 
If there are issues in a PR, a blocking comment will be made, with the prefix "Blocking: ".
Other comments will just be made without the prefix. Meaning they are suggestions, and not blocking comments.

Here is the list of what is considered blocking:
- Code that does not follow the SOLID principles.
- Risk for security issues.
- Risk for performance issues.
- Plain code logic errors.
- Code that does not follow our testing strategy, or low test coverage.
- Code that does not follow our naming conventions. Traits, abstract classes, types, interfaces.

Thing that are non-blocking:
- Small optimizations.
- Comments
- Naming that not affected by our naming conventions. methods, variables, parameters, properties.
- Spelling errors
- Readability improvements.

For external reviews (PR's from people outside the PUP team), will **Readability improvements / low readability** be blocking.

## Naming Conventions
The general naming conventions we follow in the PUP team. As we only support Scala and Node (typescript), the conventions are for these two languages.

### Scala:
- No underscore
- Classes: PascalCase
- Files: PascalCase
- Traits: prefix with T, e.g. TVehicle (exception to common convention)
- Abstract classes: prefix with Abstract, AbstractVehicle
- Package: one word, all lower case
- Variable (val): camelCase
- Method: camelCase
- ENUM: PascalCase, both enum name and values
- Tests: Suffix with Spec, VehicleSpec.scala

### Node (typescript):
- No underscores
- Classes: PascalCase
- Files: PascalCase
- Interfaces: prefix with I, e.g. IVehicle (exception to common convention)
- Types: prefix with T, e.g. TVehicle (exception to common convention)
- Folders: one word, all lower case
- Variable : camelCase
- Functions: camelCase
- Enum: PascalScase for the name and full caps for values
- Tests: file name . spec, vehicle.spec.ts


### Generel:
A repository is an abstraction over your domain model's data access.
- Main purpose: Hide the details of data access (e.g., MongoDB, SQL, files) from the domain/business logic.
- Focus: Expose high-level, domain-specific operations like findUserByEmail, saveOrder, etc.
- Returns: Domain objects (e.g. User, Order), not database-specific representations (e.g. BSON, JSON).

A client is usually a low-level wrapper around an external system (like a database, API, message queue, etc.).
- Main purpose: Directly interact with an external service or infrastructure.
- Focus: Implement the raw, lower-level operations (e.g., execute a Mongo query, call an HTTP API).
- Returns: Often deals with raw data formats (e.g. BSON documents, HTTP responses), not necessarily domain models.


- Naming of classes:
The most specific part first, e.g. VehicleMongoRepository

- Naming of methods/functions:
WhatItDoesAndOnWhat, e.g. findByEmail, saveOrder



- Abbreviations:
No thank you, (exceptions common like AWS, DNS and in comments)