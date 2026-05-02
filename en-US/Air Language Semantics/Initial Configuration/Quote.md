# Quote

## .quote.make

Type: function

Context: free

Input: relevant

Constructs a quote with input as the source.

## .quote.get_source

Type: function

Context: constant

Input: free

ctx should be a quote, outputs ctx's value.

## .quote.set_source

Type: function

Context: mutable

Input: relevant

ctx should be a quote, sets ctx's value to input, outputs ctx's original value.
