# Function

The function type represents a function.

## Context Awareness

Functions are divided into context-free, context-constant, and context-mutable functions.

### Free

A context-free function does not access or modify the context.

### Constant

A context-constant function can read the context but does not modify it.

### Mutable

A context-mutable function can both read and modify the context.

## Input Awareness

Functions are divided into input-free and input-relevant functions.

## Implementation

### Primitive Functions

Primitive functions are built into the initial configuration.

### Composite Functions

Composite functions are composed from other functions. A composite function consists of:

- Code
  - Context name (for context-aware functions)
  - Input name (for input-relevant functions)
  - Function body
- Initial context

The behavior when a composite function is called:

- The initial context is copied as the context
- The call's input is stored in the context under the input name
- If the function is context-mutable/constant, a mutable/constant link to the call's context is stored in the context under the context name
- The evaluation function is called within the context with the function body as input, and its return value is returned
