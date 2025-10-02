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
Questions about SOLID in scala, please talk to the team. And more info on SOLID in React please read here: [Link to SOLID in React](https://dev.to/mikhaelesa/series/24919)

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
// TODO: will be implemented after meeting