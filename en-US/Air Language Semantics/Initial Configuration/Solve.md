# Solve

## .solve.make

Type: function

Context: free

input should be `func : output`, outputs the solve `? func output`.

## .solve.get_function

Type: function

Context: constant

Input: free

ctx should be a solve, returns ctx's function.

## .solve.set_function

Type: function

Context: mutable

ctx should be a solve, sets ctx's function to input, returns ctx's original function value.

## .solve.get_output

Type: function

Context: constant

Input: free

ctx should be a solve, returns ctx's output.

## .solve.set_output

Type: function

Context: mutable

ctx should be a solve, sets ctx's output to input, returns ctx's original output value.
