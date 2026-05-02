# Error

## .error.abort.type

Abort type

- `.steps`: steps exhausted
- `.bug`: logic error in code

## .error.abort.message

Abort message

## .error.abort

Type: function

Context: free

Input: free

Aborts the current config's code execution.

## .error.assert

Type: function

Context: free

Input: relevant

input should be a bit, if false, aborts the current config's code execution.

## .error.is_aborted

Type: function

Context: constant

Input: free

ctx should be a config, returns whether ctx has been aborted.

## .error.recover

Type: function

Context: mutable

Input: free

ctx should be a config, recovers the aborted ctx.
