# Context

## .context.get

Type: function

Context: constant

Outputs the value bound to input.

## .context.take

Type: function

Context: mutable

Outputs the value bound to input, sets input to be bound to unit.

## .context.set

Type: function

Context: mutable

input should be `key : value`, binds `key` to `value`.

## .context.is_constant

Type: function

Returns whether the context is constant.

## .context.is

Type: function

Context: mutable

Pattern matching and assignment. Matches a single pattern; if the match succeeds, the bindings are applied.

### Match Binding

The process of matching a `pattern` against a `value`:

- If `pattern` is the key `_a` (`a` is any key), matches `a`
- If `pattern` is the key `''`, matches any value without binding
- If `pattern` is the key `a`, matches any value `v`, binds `v` to `a`
- If `pattern` is a literal `v`, matches `v`
- If `pattern` is `.(b)` (`_(b)`), matches `.(v)` (`_(v)`), recursively match-binds `v` with `b`
- If `pattern` is `b1 : b2` (`_ b1 b2`, `? b1 b2`), matches `v1 : v2` (`_ v1 v2`, `? v1 v2`), recursively:
  - Match-binds `v1` with `b1`
  - Match-binds `v2` with `b2`
- If `pattern` is `[b1, b2, ..., bn]`, matches a list `l`, recursively:
  - Match-binds the first value of `l` with `b1`
  - Match-binds the second value of `l` with `b2`
  - ...
  - Match-binds the `n`-th value of `l` with `bn`
- If `pattern` is `{k1 : b1, k2 : b2, ..., kn : bn}`, matches a map `m`, recursively:
  - Match-binds the value bound to `k1` in `m` with `b1`
  - Match-binds the value bound to `k2` in `m` with `b2`
  - ...
  - Match-binds the value bound to `kn` in `m` with `bn`

## .context.get_self

Type: function

Context: constant

Input: free

Outputs the current context.

## .context.let

Type: function

input should be `c : f : i`, looks up the context `c1` from ctx using key `c`, calls `f` with `c1` as context and `i` as input.

## .context.let.bind

Type: function

Context: free

input should be a function, outputs a function `g` such that `ctx g input` is equivalent to `ctx context.let g : input`.

Most context read/write functions export a bind function, whose key is the original function's key + `.context.let`.
