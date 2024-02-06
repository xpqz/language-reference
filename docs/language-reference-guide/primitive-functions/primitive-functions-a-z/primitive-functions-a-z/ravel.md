<div class="heading">
  <div class="name">Ravel</div>
  <div class="command">R←,Y</div>
</div>

`Y` may be any array.  `R` is a vector of the elements of `Y` taken in row-major order.

# Examples
```apl
      M
1 2 3
4 5 6
 
      ,M
1 2 3 4 5 6
 
      A
ABC
DEF
GHI
JKL
      ,A
ABCDEFGHIJKL
 
      ⍴,10
1
```

See also: [Ravel with Axes below](/ravel-with-axes.md#RavelwithAxes).
