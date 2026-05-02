# Evaluation

## Context

### Cell

- `.cell.value`: the value in the cell

### Pair

- `.pair.left`: the pair's left element
- `.pair.right`: the pair's right element

Read-write.

### List

- `.list.first`: the list's first element
- `.list.last`: the list's last element
- integer: the list's `i`-th element

Read-write.

### Map

Key `k` represents the value mapped to by `k` in the map.

Read-write, addable, removable.

### Quote

- `.quote.value`: the quote's source

### Call

- `.call.function`: the call's function
- `.call.input`: the call's input

Read-write.

### Solve

- `.solve.function`: the solve's function
- `.solve.output`: the solve's output

Read-write.

## Key

- `_a` ➔ `a`
- `.a` ➔ `.a`
- `a` ➔ `v`, where `v` is the value bound to key `a` in the context

## Quote

`_(v)` ➔ `v`

## Call

`_ f i` ➔ `f'(i')`, where `x'` denotes the result of evaluating `x`. Same below.

## Solve

`? f o` ➔ `i`, where `f'(i) = o'` is a fact in the config fact database.

## Structure

- `.(v)` ➔ `.(v')`
- `v1 : v2` ➔ `v1' : v2'`
- `[v1, v2, ..., vn]` ➔ `[v1', v2', ..., vn']`
- `{k1 : v1, k2 : v2, ..., kn : vn}` ➔ `{k1 : v1', k2 : v2', ..., kn : vn'}`

## Other

For all other values, the evaluation rule is `v` ➔ `v`.
