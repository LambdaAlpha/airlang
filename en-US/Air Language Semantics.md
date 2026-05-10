# Air Language Semantics

## Goals

- Generality
- Optimality
- Developer friendliness
- Reliability
- Maintainability
- Extensibility
- Semantic support for logic, complexity, reflection, and intelligence

## Design

- Build a minimal yet extensible semantic core; implement non-core semantics as initial context
- Build a computation-based logical framework capable of expressing any computable proposition, proof, and theorem
- Build a non-deterministic computation-based problem framework capable of expressing any computable problem, answer, and verification
- Build a complexity-based intelligence framework capable of optimally solving all computable problems
- Based on computer science theory, implement and maintain the generality of semantics and frameworks
- Use the logical framework to achieve reliability
- Use the problem framework to achieve maintainability and extensibility
- Use the intelligence framework to achieve optimality
- Maintain flexibility: make no trade-offs, defer choices
- Avoid adding language features that would break good properties (e.g., locality)
- Support sufficiently powerful reflection for self-optimization
- Naming should be accurate and memorable; avoid ambiguous abbreviations and invented terms
- Provide forward/backward compatibility and deprecation mechanisms

## Values

Values are representations of information.

Values can be constructed, discarded, copied, moved, modified, compared, etc.

[Values](./Air%20Language%20Semantics/Values.md)

## Config

A config is a container for global environment information.

A config is also a value.

[Config](./Air%20Language%20Semantics/Values/Config.md)

## Context

Context is a container for local environment information when calling a function.

Any type can serve as the context of a function call.

## Function

A function is a representation of a computational process that transforms values within a context.

A function's input and output are both values.

Functions can read and write the context.

When calling a function, the caller explicitly provides the input, while the language implicitly provides the context.

A function is also a value.

[Function](./Air%20Language%20Semantics/Values/Function.md)

## Initialization

The initialization of a computational process means starting computation by calling the initial function in the initial config with the initial context using the initial value as input.

### Initial Value

The initial value is the code provided by the user.

### Initial Config

The initial config is provided by the language.

The initial config contains important information and primitive functions.

[Initial Configuration](./Air%20Language%20Initial%20Configuration.md)

### Initial Context

The initial context is provided by `.prelude` in the initial config.

The initial context contains a small number of important or commonly used values.

[Initial Context](./Air%20Language%20Initial%20Configuration/Initial%20Context.md)

### Initial Function

The initial function is the evaluation function provided by the language.

Code is a value. The evaluation function takes code as input and outputs the result of executing the code in the current context.

The evaluation function provides the ability to read the context and call functions.

[Evaluation](./Air%20Language%20Semantics/Evaluation.md)
