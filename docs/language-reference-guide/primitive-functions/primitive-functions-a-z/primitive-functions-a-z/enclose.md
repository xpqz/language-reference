<div class="heading">
  <div class="name">Enclose</div>
  <div class="command">R←⊂Y</div>
</div>

`Y` may be any array.  `R` is a scalar array whose item is the array `Y`.  If `Y` is a simple scalar, `R` is the simple scalar unchanged.  Otherwise, `R` has a depth whose magnitude is one greater than the magnitude of the depth of `Y`.

# Examples
```apl
      ⊂1
1
 
      ⊂'A'
A
 
      ⊂1 2 3
 1 2 3
 
      ⊂1,⊂'CAT'
 1  CAT
 
      ⊂2 4⍴⍳8
 1 2 3 4
 5 6 7 8
 
      ⊂⍳0
 
      ⊂⊂⍳0
 
      ⊂⊂10
10
```

See also: [Enclose with Axes below](/enclose-with-axes.md#EnclosewithAxes).
