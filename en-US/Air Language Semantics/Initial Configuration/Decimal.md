# Decimal

## .decimal.rounding.mode

Type: key

- `.infinity`: round toward infinity
- `.zero`: round toward zero
- `.positive`: round toward positive
- `.negative`: round toward negative
- `.half_infinify`: round to nearest, ties toward infinity
- `.half_zero`: round to nearest, ties toward zero
- `.half_even`: round to nearest, ties to even
- ...

## .decimal.rounding.precision

Type: integer

A positive integer specifying the precision of decimal operation outputs.

## .decimal.add

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs the sum.

## .decimal.subtract

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs the difference.

## .decimal.multiply

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs the product.

## .decimal.divide

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs the quotient as a decimal.

## .decimal.less

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs whether `a` is less than `b`.

## .decimal.less_equal

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs whether `a` is less than or equal to `b`.

## .decimal.greater

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs whether `a` is greater than `b`.

## .decimal.greater_equal

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs whether `a` is greater than or equal to `b`.

## .decimal.less_greater

Type: function

Context: free

Input: relevant

input should be `a : b`, where `a` and `b` are decimals. Outputs whether `a` is less than or greater than `b`.
