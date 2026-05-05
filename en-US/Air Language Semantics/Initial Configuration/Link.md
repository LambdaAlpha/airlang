# Link

## .link.make

Type: function

Context: free

Input: relevant

Creates a link whose value is input.

## .link.make_constant

Type: function

Context: free

Input: relevant

Creates a constant link whose value is input.

## .link.is_constant

Type: function

Context: free

Input: relevant

input should be a link, outputs whether input is constant.

## .link.is_available

Type: function

Context: free

Input: relevant

input should be a link, outputs whether input is currently available.

## .link.get_id

Type: function

Context: constant

Input: relevant

input should be a link, outputs input's id. Links with equal ids are equal, and vice versa.

## .link.let

Type: function

Context: free

Input: relevant

input should be `link : f : i`, calls `f` with the link's value as context and `i` as input.

## .link.let.bind

Type: function

Context: free

Input: relevant

input should be a function, outputs a function `g` such that `ctx g input` is equivalent to `ctx link.let g : input`.

Most context read/write functions export a bind function, whose key is the original function's key + `.link.let`.
