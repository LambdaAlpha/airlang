# Fact

The fact database is global storage within a config, used to record function call facts (input-output mappings). It supports forward queries and reverse solving.

## .fact.put

Type: function

Context: free

input should be `func : input`, calls `func` with `input`, records the input and output to the fact database.

## .fact.call

Type: function

Context: free

input should be `func : input`, queries `func(input)` from the fact database. If found, returns the output wrapped in a cell; otherwise returns unit.

## .fact.solve

Type: function

Context: free

input should be `func : output`, reverse-solves for an input such that `func(input) = output` from the fact database. If found, returns the input wrapped in a cell; otherwise returns unit.

## .fact.exist

Type: function

Context: free

input should be `func : input : output`, checks whether the fact `func(input) = output` exists in the fact database. Returns a bit.
