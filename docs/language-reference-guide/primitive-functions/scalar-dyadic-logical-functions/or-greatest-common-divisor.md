<div class="heading">
  <div class="name">Or, Greatest Common Divisor</div>
  <div class="command">R←X∨Y</div>
</div>
# Case 1: X and Y are Boolean

R is Boolean and is determined as follows:
```apl
             X   Y     R
      
             0   0     0
             0   1     1
             1   0     1
             1   1     1
```

# Example
```apl
      0 0 1 1 ∨ 0 1 0 1
0 1 1 1
```

# Case 2: X and Y are numeric (non-Boolean)

R is the Greatest Common Divisor of `X` and `Y`. Note that in this case, `⎕CT` and `⎕DCT` are implicit arguments.

# Examples
```apl
      15 1 2 7 ∨ 35 1 4 0
5 1 2 7
 
      rational←{↑⍵ 1÷⊂1∨⍵} ⍝ rational (⎕CT) approximation
                           ⍝ to floating array.
      rational 0.4321 0.1234 6.66, ÷1 2 3
 4321  617 333 1 1 1
10000 5000  50 1 2 3
```
