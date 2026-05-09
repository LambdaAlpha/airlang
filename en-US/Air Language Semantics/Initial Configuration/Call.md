# Call

## .call.make

Type: function

Context: constant

input should be `func : input`, outputs the call `_ func input`.

## .call.get_function

Type: function

Context: constant

Input: free

ctx should be a call, returns ctx's function.

## .call.set_function

Type: function

Context: mutable

ctx should be a call, sets ctx's function to input, returns ctx's original function value.

## .call.get_input

Type: function

Context: constant

Input: free

ctx should be a call, returns ctx's input.

## .call.set_input

Type: function

Context: mutable

ctx should be a call, sets ctx's input to input, returns ctx's original input value.
