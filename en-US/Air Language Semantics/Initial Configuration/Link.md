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

## .link.which

Type: function

Context: free

Input: relevant

input should be `link : f : i`, calls `f` with the link's value as context and `i` as input.
