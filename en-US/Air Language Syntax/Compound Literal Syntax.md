# Compound Literal Syntax

## Cell

- `.(v)`
- `.'text'`
- `."text"`
- `.[l, i, s, t]`
- `.{a : map}`

Examples:

```air
.(true)
.('cell')
.(.[.{a : .""}])
```

## Pair

`a : b`

- `_ : b`  equals `b`
- `a : _`  equals `a`
- `_ : _`  equals `.`

Examples:

```air
a : b
a : []
[] : a
a : b : c
(a : b) : c
a : (b c)
(a b) : c
a : (b [])
(a []) : b
a : _ b c
(_ a b) : c
a : b c d
(a b c) : d
```

## List

`[a, b, ..., z]` or `[a, b, ..., z,]`

`#[a b ... z]`

Examples:

```air
[]
[a]
[a,]
[a, b]
[a, b,]
[a, b, c]
[a, b, c,]
#[]
#[a]
#[a b]
#[a b c]
```

## Map

`{k1 : v1, ..., kn : vn}` or `{k1 : v1, ..., kn : vn,}`

`#{k1 v1 ... kn vn}`

Where each `ki` is a key. Keys in a map must not repeat.

If a key-value pair's value is unit, the value can be omitted. E.g., `{a : ., b : c}` can be abbreviated as `{a, b : c}`.

Examples:

```air
{}
{a : b}
{a : b,}
{a : b, c : d}
{a : b, c : d,}
{a : b, c : d, e : f}
{a : b, c : d, e : f,}
{a}
{a,}
{a, b}
{a, b,}
{a, b : c}
{a : b, c}
#{}
#{a b}
#{a b c d}
#{
a b
c d
e f
}
```

## Quote

- `_(v)`
- `_'text'`
- `_"text"`
- `_[l, i, s, t]`
- `_{a : map}`

Examples:

```air
_(true)
_('quote')
_(_[_{a : _""}])
```

## Call

- `_ f a`: `f` is the function, `a` is the input
- `a f _`: `f` is the function, `a` is the input
- `a f b`: `f` is the function, `a : b` is the input

Examples:

```air
_ a b
_ a _ b c
_ a []
_ a b : c
a f b
a f b g c
a f _ g b
_ f a g b
_ f _ g a
```

## Solve

- `? f a`: `f` is the function, `a` is the output
- `a f ?`: `f` is the function, `a` is the output

Examples:

```air
? a b
? a ? b c
? a []
? a b : c
a f ? g b
? f a g b
```
