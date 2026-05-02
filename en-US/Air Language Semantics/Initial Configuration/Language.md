# Language

## .language.semantics.eval

Type: function

Context: mutable

Input: relevant

Evaluates input.

## .language.syntax.parse

Type: function

Context: free

Input: relevant

input should be a text, parses input using Air syntax into a value `v`, returns `.(v)`.

## .language.syntax.generate_pretty

Type: function

Context: constant

Input: free

Returns ctx's Air syntax representation as text.

## .language.syntax.generate_key

Type: function

Context: constant

Input: free

Returns ctx's Air key representation. Two values being equal is equivalent to their keys being equal.

## .language.syntax.is_valid

Type: function

Context: constant

Input: free

Returns whether ctx is a syntax value.

## .language.version

Type: list

The language `major : minor : patch`
