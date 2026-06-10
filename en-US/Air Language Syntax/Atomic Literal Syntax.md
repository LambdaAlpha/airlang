# Atomic Literal Syntax

## Unit

`.`

## Bit

`true` represents true.

`false` represents false.

## Text

`"xxx"'xxx'(xxx)[xxx]`

Starts in single-bracket or double-bracket mode.

Supports the Unicode character set.

### Single-Bracket Mode

`'xxx'` — single-bracket mode.

- Must not contain `'`

### Double-Bracket Mode

`"xxx"` — double-bracket mode.

- Must not contain `"`

### Comment Mode

`(xxx)` — comment mode.

- Must not contain `)`
- All characters are ignored

### Lexical Mode

`[xxx]` — lexical mode.

In lexical mode, one word represents one character. Words are separated by spaces.

ASCII printable characters except space and `]` can represent themselves with a single character, e.g., `a` represents `a`.

ASCII control characters and space use standard ASCII symbol notation:

| HEX | Symbol |
| --- | --- |
| 00 | nul |
| 01 | soh |
| 02 | stx |
| 03 | etx |
| 04 | eot |
| 05 | enq |
| 06 | ack |
| 07 | bel |
| 08 | bs |
| 09 | ht |
| 0A | lf |
| 0B | vt |
| 0C | ff |
| 0D | cr |
| 0E | so |
| 0F | si |
| 10 | dle |
| 11 | dc1 |
| 12 | dc2 |
| 13 | dc3 |
| 14 | dc4 |
| 15 | nak |
| 16 | syn |
| 17 | etb |
| 18 | can |
| 19 | em |
| 1A | sub |
| 1B | esc |
| 1C | fs |
| 1D | gs |
| 1E | rs |
| 1F | us |
| 20 | sp |
| 7F | del |

All Unicode characters can be expressed using hexadecimal code points prefixed with `X`, with lowercase digits, e.g., `X1f701` represents 🜁.

### Line Splitting

For long or complex text, line-splitting forms can be used.

No mode can contain a line break; before a line break, the current mode must be ended first, followed by `_` (no line break), `.` (lf), or `:` (crlf), then lf or crlf. Carriage return must be followed by line feed. To represent a standalone carriage return, use `cr` in lexical mode. Spaces and tabs after the line break are ignored.

Examples:

```air
'🜁: Alchemical Symbol For Air'
➔ 🜁: Alchemical Symbol For Air

"'a'"(this is a comment)[X1f701 ' " sp ht cr lf]'"a"'
➔ 'a'🜁'" \t\r\n"a"

    "()[]{}<>\|/'"_
    '"`^*+=-~_.,:;!?@#$%&'_
    (this is a comment)_
    [X1f701 ' " sp ht cr lf]
➔ ()[]{}<>\|/'"`^*+=-~_.,:;!?@#$%&🜁'" \t\r\n
```

## Key

### Literal Form

`xxx`

Most keys can be written in literal form. The following keys cannot:

- The empty key
- Keywords
- Keys starting with a digit
- Keys containing delimiters

Examples:

- `a` represents `a`
- `~` represents `~`
- `!!` represents `!!`

```air
a
a_string
str2
%
+
+=
+u
->
;a
a;
:a
a:
?a
a?
;
':'
!
?
```

### Canonical Form

`key'xxx'"xxx"(xxx)[xxx]`

Prefixed with `key`, followed by text syntax.

Examples:

```air
>=
➔ >=

a.b.c
➔ a.b.c

key'[0, 1, 2]'
➔ [0, 1, 2]

key'"a"'(this is a comment)[X3f ' " ) ( sp]"'a'"
➔ "a"?'")( 'a'

key'abcdefghijklmnopqrstuvwxyz'_
"()[]{}<>\|/'"_
'"`^*+=-~_.,:;!?@#$%&'_
(this is a comment)_
[sp 0 1 2 3 4 5 6 7 8 9]_
'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
➔ abcdefghijklmnopqrstuvwxyz()[]{}<>\|/'"`^*+=-~_.,:;!?@#$%& 0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ
```

## Integer

`integer'a'` or `0a`

An integer `a` consists of a sign (`+` or `-` or none), a base (`BDX`), and a digit sequence (`0-9a-f`).

`+` may be omitted. Base `D` may be omitted. `0` must be unsigned.

`B` — binary, `D` — decimal, `X` — hexadecimal.

The digit sequence must not be empty.

In the `integer'a'` syntax, `a` follows text syntax rules.

A decimal positive integer `integer'+Da'` or `0+Da` may be abbreviated as `a`.

Examples:

```air
0
123
0-123
0+123
1000000
0B1
0-B1
0B10
0B1100_0011
0Xa
0-Xa
0Xab_c
integer'123'
integer'-123'
integer'+123'
integer'D123'_'456'_'789'
integer'B0011'
integer'-Xff'
```

## Decimal

`decimal'a'` or `0a`

In the `decimal'a'` syntax, `a` follows text syntax rules.

### Common Form

A decimal `a` consists of a sign (`+` or `-` or none), an integer part (digit sequence), a decimal point (`.`), and a fractional part (digit sequence).

`0` must be unsigned.

A decimal positive number `decimal'+Da'` or `0+Da` may be abbreviated as `a`.

Examples:

```air
1.0
1.
0-1.23
0-12.34
decimal'1.'
decimal'-1.0'
```

### Canonical Form

A decimal `a` consists of a sign (`+` or `-` or none), an exponent (`E` sign digit-sequence), a multiplication sign (`*`), and a significand (digit `.` digit-sequence).

`+` may be omitted.

If `a` is 0, it must be unsigned. If the exponent is 0, it must be unsigned. If `a` is not 0, the first digit of the significand must not be 0.

Examples:

```air
0E0*1.0
0E-1*1.
0-E8*1.23
decimal'E1*1.0'
decimal'-E-8*1.234'_'567'
```

## Byte

`byte'a'`

`a` follows text syntax, consisting of a base (`BX`) and a digit sequence.

`B` — binary, followed by a sequence of binary digits (`01`), eight per unit. The sequence may be empty.

`X` — hexadecimal (omittable), followed by a sequence of hexadecimal digits (`0-9a-f`), two per unit. The sequence may be empty.

Examples:

```air
byte''
byte'B'
byte'B00001111'
byte'B00001111'_'11110000'
byte'X'
byte'X00'_'ffff'_'00'
byte'00'_'ff'
```
