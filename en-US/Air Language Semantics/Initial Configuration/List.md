# List

## .list.get_length

Type: function

Context: constant

Input: free

ctx should be a list, outputs ctx's length.

## .list.set

Type: function

Context: mutable

Input: relevant

input should be `i : v`, ctx should be a list, sets ctx's `i`-th item to `v`, outputs the `i`-th item's original value.

## .list.set_many

Type: function

Context: mutable

Input: relevant

input should be `i : vs`, where `len` is the length of the list `vs`, ctx should be a list, sets ctx's items from `i` through `i + len - 1` to `vs`, outputs a list of the replaced items' original values.

## .list.get

Type: function

Context: constant

Input: relevant

input should be an integer `i`, ctx should be a list, outputs ctx's `i`-th item's value.

## .list.get_many

Type: function

Context: constant

Input: relevant

input should be a pair `begin : end`, ctx should be a list.

- If `begin` is unit, set `begin` to `0`
- If `end` is unit, set `end` to ctx's length
- Outputs ctx's items from `begin` to `end - 1` as a list

## .list.insert

Type: function

Context: mutable

Input: relevant

input should be `i : v`, ctx should be a list, inserts `v` after ctx's `i`-th item.

## .list.insert_many

Type: function

Context: mutable

Input: relevant

input should be `i : vs`, ctx should be a list, inserts all elements of the list `vs` after ctx's `i`-th item.

## .list.remove

Type: function

Context: mutable

Input: relevant

input should be an integer `i`, ctx should be a list, removes and outputs ctx's `i`-th item.

## .list.remove_many

Type: function

Context: mutable

Input: relevant

input should be a pair `begin : end`, ctx should be a list.

- If `begin` is unit, set `begin` to `0`
- If `end` is unit, set `end` to ctx's length
- Removes and outputs ctx's items from `begin` to `end - 1` as a list

## .list.push

Type: function

Context: mutable

Input: relevant

ctx should be a list, inserts input at the end of ctx.

## .list.push_many

Type: function

Context: mutable

Input: relevant

ctx should be a list, input should be a list, inserts all elements of input at the end of ctx.

## .list.pop

Type: function

Context: mutable

Input: relevant

ctx should be a list, removes 1 element from the end of ctx and returns it.

## .list.pop_many

Type: function

Context: mutable

Input: relevant

ctx should be a list, removes input elements from the end of ctx and returns them as a list.

## .list.clear

Type: function

Context: mutable

Input: free

ctx should be a list, clears ctx.
