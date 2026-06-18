# Control

## .control.do

Type: function

input should be a list, executes the elements `si` of input in order, outputs the evaluation result of the last element.

- If `si` is a call `_ .try i`, evaluate `i` to obtain `c`. If `c` is `.(v)`, stop evaluating subsequent elements and output `v`
- Otherwise evaluate `si`

## .control.then

Type: function

input should be `condition : branches`, `branches` should be `branch1` or `branch1 : branch2`

- If `condition` is true, execute `branch1` and output the result (execution follows the `do` pattern)
- If `condition` is false and `branch2` exists, execute `branch2` and output the result (execution follows the `do` pattern)

## .control.branch

Type: function

input should be `value : branches`

- If `branches` is a map, execute the mapped value of `value` in `branches`
- If `branches` is `map : default`
  - If key `value` exists in the map `map`, execute its mapped value
  - Otherwise execute `default`

## .control.match

Type: function

input should be `value : list`

- Match each list item `pattern : body`'s `pattern` against `value` one by one. If the match succeeds, apply bindings, execute `body`, and output the result (execution follows the `do` pattern)

## .control.loop

Type: function

input should be `condition : body`

1. Execute `condition`, obtaining `c`
2. If `c` is not true, output unit
3. Otherwise, execute `body` (execution follows the `do` pattern)
   - If the result is `.(v)`, output `v`
   - Otherwise go to 1

## .control.each

Type: function

Context: mutable

input should be `value : name : body`. If `value` is of the following types, iterate over `value`, bind the corresponding value to `name`, then execute `body` (execution follows the `do` pattern). If the result is `.(v)`, output `v`; otherwise continue iterating.

- integer: if `i` >= `0`, iterate from `0` (inclusive) to `i` (exclusive)
- byte: iterate over each byte
- key: iterate over each character
- text: iterate over each character
- list: iterate over each item
- map: iterate over each key-value pair
