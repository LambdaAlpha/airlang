# Air Language Syntax

## Goals

- Decoupled syntax and semantics
- Strong expressiveness
- High readability
- Unambiguous
- Simple rules, easy to understand
- Linear parse time
- Limited and controllable extensibility

## Design

- Express only semantically irrelevant information; defer computation to the semantic interpretation stage
- Use calls and solves to express any semantics
- Provide contextual syntax: switch parsing rules based on context
- Provide non-combining syntax for custom syntax
- Provide structured comment syntax

## Whitespace

Whitespace is text composed of sequences of space (` `), tab (`ht`), and newline (`lf`, `cr lf`).

Whitespace separates tokens.

## Graphic Characters

All graphic characters in the ASCII range, from space (` `) (32, inclusive) to `~` (126, inclusive).

- Letters (`a-zA-Z`)
- Digits (`0-9`)
- Punctuation (`` `~!@#$%^&*()_+-=[]{}\|;:'",.<>/? ``)
- Space (` `)

## Key

A key is a sequence of graphic characters.

## Keywords

- `_`
- `.`
- `:`
- `?`
- `true`
- `false`

## Delimiters

Delimiters are keys used to determine token boundaries.

- ` `
- `,`
- `(`, `)`
- `[`, `]`
- `{`, `}`
- `'`
- `"`

## Key Form

A key form is a syntactic form composed of a key that contains no delimiters. Examples:

```air
.
true
false
abc
1.23E-3
>=
```

## Delimited Form

A delimited form is a syntactic form whose boundaries are determined by paired delimiters.

- `'a'`
- `"a"`
- `(a)`
- `[a]`
- `{a}`

## Prefixed Delimited Form

A prefixed delimited form is a syntactic form whose boundaries and parsing rules are determined by a prefix and delimiters.

- `a'b'`
- `a"b"`
- `a(b)`
- `a[b]`
- `a{b}`

Prefixed delimited forms are extensible, unambiguous syntactic forms.

## Syntax Forms

Key forms, delimited forms, and prefixed delimited forms are collectively called bounded forms.

An unbounded form is a sequence of bounded forms separated by whitespace.

All syntax forms are either bounded forms or unbounded forms.

## Comments

- `!(t1 t2 ... tn)`
- `!'key'`
- `!"text"`
- `![l, i, s, t]`
- `!{a : map}`

Comment content is discarded during parsing. Comment content is a sequence of:

- Whitespace
- Comments
- `,`
- Bounded-form tokens

```air
!"comment"
[1, !(2, 3,) 4]
{a : !(1, b :) 2}
```

## Scopes

A scope is a delimited form (`(a)`) or prefixed delimited form (`a(b)`). Parsing inside and outside a scope is independent; parsing outside a scope does not depend on syntactic features inside.

Scopes can provide syntactic contexts. A scope inherits the outer scope's context and modifies part of the configuration.

Root scope context: right-associative.

### Empty Scope

`(a)`

An empty scope inherits the outer scope's context without modifying any configuration.

Empty scopes enhance readability and assist syntax parsing.

Examples:

```air
(a)
(a b c)
(a b c) : d
a b (c : d)
```

### Associativity Scope

`<(a)` or `>(a)`

Left-associative or right-associative within the scope.

Examples:

```air
<(a b c d e) === (a b c) d e
<(a) === a
<(a b) === a b
<(a b c) === a b c
<(a : b) === a : b
>(a b c d e) === a b (c d e)
>(a) === a
>(a b) === a b
>(a b c) === a b c
>(a : b) === a : b
```

## Literals

### Atomic Literals

Atomic literals use uppercase letters or non-letter symbols to separate segments.

[Atomic Literal Syntax](./Air%20Language%20Syntax/Atomic%20Literal%20Syntax.md)

### Compound Literals

[Compound Literal Syntax](./Air%20Language%20Syntax/Compound%20Literal%20Syntax.md)

## Reference

[Syntax Reference](./Air%20Language%20Syntax/Syntax%20Reference.md)
