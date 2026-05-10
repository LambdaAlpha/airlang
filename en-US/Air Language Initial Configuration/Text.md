# Text

## .text.from_utf8

Type: function

Context: free

input should be a valid UTF-8 encoded byte, converts input to text.

## .text.into_utf8

Type: function

Context: free

input should be a text, converts input to a UTF-8 encoded byte.

## .text.get_length

Type: function

Context: constant

Input: free

ctx should be a text, outputs ctx's length.

## .text.push

Type: function

Context: mutable

input should be a text, ctx should be a text, appends input to ctx.

## .text.join

Type: function

Context: free

input should be a list of texts, joins input into a text.
