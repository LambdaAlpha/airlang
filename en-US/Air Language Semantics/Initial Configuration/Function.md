# Function

## .function.make

Type: function

Context: free

Input: relevant

Constructs a function.

input should be a map

- code: representation of the call process, `(ctx : input) : body`, where `ctx` is the context variable name or unit, `input` is the input variable name or unit, `body` is the function body
- prelude: initial context
- constant: whether the context is constant

## .function.represent

Type: function

Context: free

Input: relevant

Represents a function. Outputs a map

- code: representation of the call process, `(ctx : input) : body`, where `ctx` is the context variable name, `input` is the input variable name, `body` is the function body
- prelude: initial context
- constant: whether the context is constant

## .function.is_free

Type: function

Context: constant

Input: free

ctx should be a function, outputs whether ctx is context-free.

## .function.is_constant

Type: function

Context: constant

Input: free

ctx should be a function, outputs whether ctx is context-constant.

## .function.is_input_free

Type: function

Context: constant

Input: free

ctx should be a function, outputs whether ctx is input-free.

## .function.is_primitive

Type: function

Context: constant

Input: free

ctx should be a function, outputs whether ctx is a primitive function.

## .function.get_code

Type: function

Context: constant

Input: free

ctx should be a function, outputs ctx's code representation.

## .function.get_prelude

Type: function

Context: constant

Input: free

ctx should be a function, outputs ctx's initial context.

## .function.get_id

Type: function

Context: constant

Input: free

ctx should be a function, outputs ctx's id. Function equality is equivalent to id equality.
