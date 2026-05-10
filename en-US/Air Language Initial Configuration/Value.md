# Value

## .value.any

Context: free

If input is unit, outputs an arbitrary value.
If input is `.syntax`, outputs a syntax value.
If input is a key representing a type (see `type`), outputs an arbitrary value of that type.

This function makes no guarantees about the output, including randomness.

## .value.get_type

Context: constant

Input: free

Outputs a key representing ctx's type.

- Unit: `.unit`
- Bit: `.bit`
- Integer: `.integer`
- Decimal: `.decimal`
- Byte: `.byte`
- Key: `.key`
- Text: `.text`
- Cell: `.cell`
- Pair: `.pair`
- List: `.list`
- Map: `.map`
- Quote: `.quote`
- Call: `.call`
- Link: `.link`
- Config: `.config`
- Function: `.function`
- Other extension types

## .value.equal

Type: function

Context: constant

input should be a pair, compares the left value `v1` and right value `v2` for equality. Functions and links are compared by copy identity; other built-in types use structural equality.
