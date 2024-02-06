<div class="heading">
  <div class="name">Not Equal</div>
  <div class="command">R←X≠Y</div>
</div>

`Y` may be any array.  `X` may be any array.  `R` is Boolean.  `R` is 0 if `X=Y`.  Otherwise `R` is 1.

For Boolean `X` and `Y`, the value of `R` is the exclusive or (XOR)  result, determined as follows:
```apl
             X   Y     R
      
             0   0     0
             0   1     1
             1   0     1
             1   1     0
```

`⎕CT` and `⎕DCT` are  implicit arguments of Not Equal.

# Examples
```apl
      1 2 3 ≠ 1.1 2 3
1 0 0
 
      ⎕CT←1E¯10
 
      1≠1 1.00000000001 1.0000001
0 0 1
 
      1 2 3 ≠'CAT'
1 1 1
```
