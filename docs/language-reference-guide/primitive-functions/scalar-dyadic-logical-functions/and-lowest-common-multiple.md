<div class="heading">
  <div class="name">And, Lowest Common Multiple</div>
  <div class="command">R←X^Y</div>
</div>
# Case 1: X and Y are Boolean

`R` is Boolean is determined as follows:
```apl
             X   Y     R
      
             0   0     0
             0   1     0
             1   0     0
             1   1     1
```

Note that the ASCII caret (^) will also be interpreted as an APL And (`^`).

# Example
```apl
      0 1 0 1 ^ 0 0 1 1
0 0 0 1
```

# Case 2: Either or both X and Y are numeric (non-Boolean)

`R` is the lowest common multiple of `X` and `Y`. Note that in this case, `⎕CT` and `⎕DCT` are implicit arguments.

# Example
```apl
      15 1 2 7 ^ 35 1 4 0
105 1 4 0
 
      2 3 4 ∧ 0j1 1j2 2j3
0J2 3J6 8J12
 
      2j2 2j4 ∧ 5j5 4j4
10J10 ¯4J12
```
