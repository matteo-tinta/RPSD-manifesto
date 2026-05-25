---
name: "test-driven-development"
description: "Use this skill as an unbreakable baseline for writing any type of code. This skill provides guidelines and conventions for writing code, including how to structure your tests, how to write testable code, and how to refactor your code while keeping it covered by tests. More instructions may be added in the project"
---

# Skill Workflow
1. *red phase*: Write unit tests first that define the expected behavior of the component. Tests should be specific, covering edge cases and error handling.
2. *green phase*: Implement the component with the minimum code necessary to make the tests pass.
3. *refactor phase*: Refactor the code for readability, maintainability, and performance while ensuring all tests still pass.

# Guidelines
- *small files*: over big files. files should be small and focused, ideally under 100 lines of code.
- *short code*: over long code. components and functions should do one thing and do it well. Readable, within 5 cyclomatic complexity
- *descriptive naming*: use clear and descriptive names for functions, variables, and files that convey their purpose and behavior.
- *consistent patterns*: follow existing patterns and conventions in the codebase for component structure, state management, and testing. Avoid introducing new patterns unless necessary.
- *test coverage*: ensure that all critical paths, edge cases, and error handling are covered by tests. Strive for high test coverage while avoiding redundant tests.
- *lazy*: do the minimum work necessary to achieve the desired behavior. Avoid over-engineering or adding unnecessary features or abstractions.

# Tests Conventions
- *Arrange, Act, Assert*: structure tests with clear sections for setup, execution, and verification.
- *Test one thing*: each test should verify one specific behavior or case.
- *Descriptive names*: test names should clearly describe the behavior being tested.
- *Prefer Implicit testing*: over multiple tests. Avoid unnecessary setup or assertions -> assert a behaviour is already covered before creating a new test

# Patterns and Principles
- *KISS*: keep it simple and straightforward. Avoid unnecessary complexity or over-engineering.
- *DRY (in patterns)*: reuse existing patterns and abstractions in the codebase. Avoid creating new ones unless necessary.
- *SOLID*: follow solid principles for object-oriented design, especially SRP and OCP.

> SRP (Single Responsibility Principle): a component should have only one reason to change, meaning it should be linked to one and just one actor.