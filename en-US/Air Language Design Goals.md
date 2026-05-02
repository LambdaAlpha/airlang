# Air Language Design Goals

## Generality and Completeness

- Turing-complete
- Easy to bootstrap
- Unified expression and complete expressiveness; usable as a data description language
- Forwards and backwards compatible; seamless upgrades

## Optimality

- Near-theoretically-optimal on any metric
- Simpler semantics → shorter code → better performance
- High expressiveness, high code reusability
- High development efficiency, low maintenance cost
- Fast execution
- Low memory usage

## Developer Friendliness

- Simple, rational design; beginner-friendly, enjoyable, easy to pick up
- Simpler semantics → shorter code → better performance
- Convenient debugging
- High code readability; non-extensible syntax; simple, easy-to-learn syntax rules
- High code understandability; low cognitive burden
- Helps developers improve, elevates code quality, deepens programming understanding
- Internationalization

## Reliability

- Formal technical specification for the language design
- Protocol-oriented programming: express, implement, prove, and verify any requirement or constraint
- Can act as a pure information processing tool; language as sandbox, no OS interaction

## Maintainability

- Protocol-oriented programming: express, implement, prove, and verify any requirement or constraint
- Flexibility: modules collaborate via protocols, localizing module impact; module implementations can change while still satisfying protocols
- Forwards and backwards compatible protocols
- Understandability: non-extensible syntax
- Portability: can be interpreted, or compiled to LLVM

## Extensibility

- Fully modular: language features encapsulated as modules; new features released as modules
- Modules are first-class objects
- Modules can enhance all aspects of the system, except syntax
- Modules collaborate via protocols; protocols have full expressiveness
- Standardized way to use any other language or application resource
- Provides FFI

## Logic

- Provides a more expressive logical framework, replacing type systems
- All mainstream logic and type systems provided as standard libraries
- Provides formal technical specification for the language design

## Complexity

- Provides a framework for expressing and analyzing complexity
- Provides complexity-based resource allocation: simpler semantics → shorter code → better performance
- Richer complexity calculation and analysis tools as standard libraries

## Reflection

- Self-hosting
- Provides a reflection framework
- Richer reflection analysis tools as standard libraries
- Provides the ability to perceive context, understand code, and modify context

## Intelligence

- Reasonably defines intelligence; basic intelligence modules provided as standard libraries
- Intelligence is additive: more intelligence modules → smarter system
- Provides code understanding capability
- Has self-improvement capability

## Non-Goals

- Does not attempt theoretically impossible tasks
- Makes no trade-offs at the language level, except for syntax
- Non-extensible syntax
- No macros or any preprocessing; everything is executed at runtime
- Indentation is not strict
- No excessive use of invented symbols
