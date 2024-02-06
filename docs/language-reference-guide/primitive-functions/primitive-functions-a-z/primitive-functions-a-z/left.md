<div class="heading">
  <div class="name">Left</div>
  <div class="command">R←X⊣Y</div>
</div>

`X` and `Y` may be any arrays.

The result `R` is the left argument `X`.

# Example
```apl
      42⊣'abc' 1 2 3
42
```

Note that when `⊣` is applied using reduction, the derived function selects the first sub-array of the array along the specified dimension. This is implemented as an idiom.

# Examples
```apl
      ⊣/1 2 3
1
 
      mat←↑'scent' 'canoe' 'arson' 'rouse' 'fleet'
      ⊣⌿mat  ⍝ first row                          
scent
      ⊣/mat  ⍝ first column                       
scarf
```
```apl
      ⊣/[2]2 3 4⍴⍳24 ⍝ first row from each plane
 1  2  3  4
13 14 15 16
```

Similarly, with expansion:
```apl
      ⊣\mat
sssss
ccccc
aaaaa
rrrrr
fffff
      ⊣⍀mat
scent
scent
scent
scent
scent
```
