# Map

## .map.get_length

Type: function

Context: constant

Input: free

ctx should be a map, outputs ctx's length.

## .map.get_items

Type: function

Context: constant

Input: free

ctx should be a map, outputs ctx's key-value pairs as a list.

## .map.into_items

Type: function

Context: mutable

Input: free

ctx should be a map, removes and outputs ctx's key-value pairs as a list.

## .map.get_keys

Type: function

Context: constant

Input: free

ctx should be a map, outputs ctx's keys as a list.

## .map.into_keys

Type: function

Context: mutable

Input: free

ctx should be a map, removes and outputs ctx's keys as a list.

## .map.get_values

Type: function

Context: constant

Input: free

ctx should be a map, outputs ctx's values as a list.

## .map.into_values

Type: function

Context: mutable

Input: free

ctx should be a map, removes and outputs ctx's values as a list.

## .map.contain

Type: function

Context: constant

Input: relevant

input should be a key, ctx should be a map, outputs whether ctx contains input.

## .map.contain_all

Type: function

Context: constant

Input: relevant

input should be a list, ctx should be a map, outputs whether ctx contains all keys in input.

## .map.contain_any

Type: function

Context: constant

Input: relevant

input should be a list, ctx should be a map, outputs whether ctx contains any key in input.

## .map.set

Type: function

Context: mutable

Input: relevant

input should be `k : v`, ctx should be a map, sets the value bound to key `k` in ctx to `v`, outputs a cell containing the original bound value.

## .map.set_many

Type: function

Context: mutable

Input: relevant

input should be a map, ctx should be a map, sets the key-value pairs from input into ctx, outputs a map of these keys' original values in ctx.

## .map.get

Type: function

Context: constant

Input: relevant

input should be a key, ctx should be a map, outputs a cell containing the value bound to input in ctx.

## .map.get_many

Type: function

Context: constant

Input: relevant

input should be a list of keys, ctx should be a map, outputs a map of the values bound to the keys in input within ctx.

## .map.remove

Type: function

Context: mutable

Input: relevant

input should be a key, ctx should be a map, removes and outputs a cell containing the value bound to input in ctx.

## .map.remove_many

Type: function

Context: mutable

Input: relevant

input should be a list of keys, ctx should be a map, removes and outputs a map of the values bound to the keys in input within ctx.

## .map.move

Type: function

Context: mutable

Input: relevant

input should be a key, ctx should be a map, removes and outputs the value bound to input in ctx.

## .map.clear

Type: function

Context: mutable

Input: free

ctx should be a map, clears ctx.

## .map.make

Type: function

Context: free

Input: relevant

input should be a list of key-value pairs, constructs a map from input.

## .map.make_set

Type: function

Context: free

Input: relevant

input should be a list of keys, constructs a map from input with all values set to unit.
