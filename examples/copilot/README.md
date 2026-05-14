# Copilot Example

> This is a basic example of RPSD in practice, with an example codebase, outcomes and results

- [Project](#the-project): include how the project is structured 
    - [Docs](#docs): include where to find usefull information about the project
    - [Codebase](#codebase): include a brief description about the codebase
    - [Discovery](#discovery-docs): include a description about discovery docs
    - [Features](#features): explain where agents dump artifacts

## The project

### Codebase
All the actual code lies inside `codebase/` folder.

#### Stack
- React (No Typescript)

#### Code Standards
Follow this code style STRICTLY

## Coding Principles
- Stick with DRY: "Don't repeat yourself"
- Stick with SOLID without overengeenering it - write maintainable and scalable code
- Stick with KISS: "Keep it simple, stupid!"
- Small, pure functions over large/impure ones
- Functional > OOP; composition > inheritance; immutability > mutability

### Docs
> Docs contains all the docs about the services, BUT NOT THE JSON CONTRACTS/API. 
> Just plain explainations of goal of single services
> MUST be kept readonly!
```
docs/
├── README.md                           Where to find what: Contains the main INDEX of the docs, in human readable format.
├── CONTRIBUTING.md                     How to contribute to the docs and the whole scaffolding of the docs
```

### Discovery Docs
> Discovery docs contains the agentic discoveries through RPSD (Research, Plan, Spike then Develop) pattern

discovery/

### Features
> Features folder is where agents stores their thinking, and output files

features/<feature-name>/

### Constraints
> Here is the list of constraints that must ALWAYS be followed


*Update this file to keep AI agents, and Human on the same level with your project's best practices.*

