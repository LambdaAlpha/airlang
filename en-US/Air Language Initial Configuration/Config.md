# Config

## .config.exist

Type: function

Context: free

input should be a key, checks whether input exists in cfg.

## .config.import

Type: function

Context: free

input should be a key, imports the value of input from cfg.

## .config.export

Type: function

Context: free

input should be `key : value`, exports `value` to cfg under `key`.

## .config.get_length

Type: function

Context: free

Input: free

Gets the length of cfg.

## .config.with

Type: function

input should be `map : body`, overwrites cfg with the key-value pairs in `map`, executes `body`, obtaining `o`, restores cfg, returns `o`.

## .config.get_self

Type: function

Context: free

Input: free

Gets cfg.

## .config.let

Type: function

Context: mutable

input should be `cfg : body`, looks up the context `c1` from cfg using key `cfg`, executes `body` with map `c1` as config and `c1`'s initial context as context. Returns `output : aborted`, where `output` is the output of executing `body`, and the bit `aborted` indicates whether the execution process has been aborted.
