<div class="heading">
  <div class="name">Nor</div>
  <div class="command">R←X⍱Y</div>
</div>

`Y` must be a Boolean array.  `X` must be a Boolean array.  `R` is Boolean.  The value of `R` is the truth value of the proposition "neither `X` nor `Y`", and is determined as follows:
```apl
             X   Y     R
      
             0   0     1
             0   1     0
             1   0     0
             1   1     0
```

# Example
```apl
      0 0 1 1 ⍱ 0 1 0 1
1 0 0 0
```
