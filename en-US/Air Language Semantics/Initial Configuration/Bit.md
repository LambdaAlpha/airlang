# Bit

## .bit.not

Type: function

Context: free

Input: relevant

- If input is true, output false
- If input is false, output true

## .bit.and

Type: function

Context: free

Input: relevant

input should be `b1 : b2`, where `b1` and `b2` are bits

- If `b1` is true and `b2` is true, output true
- Otherwise output false

## .bit.or

Type: function

Context: free

Input: relevant

input should be `b1 : b2`, where `b1` and `b2` are bits

- If `b1` is true or `b2` is true, output true
- Otherwise output false

## .bit.xor

Type: function

Context: free

Input: relevant

input should be `b1 : b2`, where `b1` and `b2` are bits

- If `b1` is true and `b2` is false, output true
- If `b1` is false and `b2` is true, output true
- Otherwise output false

## .bit.imply

Type: function

Context: free

Input: relevant

input should be `b1 : b2`, where `b1` and `b2` are bits

- If `b1` is true and `b2` is false, output false
- Otherwise output true
