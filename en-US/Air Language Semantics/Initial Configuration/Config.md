# Config

## .config.make

Type: function

Context: free

Input: relevant

input should be a map, constructs a config from input.

## .config.represent

Type: function

Context: free

Input: relevant

input should be a config, represents input as a map.

## .config.exist

Type: function

Context: free

Input: relevant

input should be a key, checks whether input exists in cfg.

## .config.import

Type: function

Context: free

Input: relevant

input should be a key, imports the value of input from cfg.

## .config.export

Type: function

Context: free

Input: relevant

input should be `key : value`, exports `value` to cfg under `key`.

## .config.get_length

Type: function

Context: constant

Input: free

ctx should be a config, gets the length of cfg.

## .config.with

Type: function

Context: mutable

Input: relevant

input should be `map : body`, overwrites cfg with the key-value pairs in `map`, executes `body`, obtaining `o`, restores cfg, returns `o`.

## .config.get_self

Type: function

Context: free

Input: free

Gets cfg.

## .config.where

Type: function

Context: mutable

Input: relevant

input should be `cfg : body`, looks up the context `c1` from cfg using key `cfg`, executes `body` with `c1` as config and `c1`'s initial context as context.
