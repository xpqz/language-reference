<div class="heading">
  <div class="name">Right</div>
  <div class="command">R←X⊢Y</div>
</div>

`X` and `Y` may be any arrays. The result `R` is the right argument `Y`.

# Examples
```apl
      42 ⊢'abc' 1 2 3
 abc  1 2 3
```
```apl
      32+1.8×⊢0 100      ⍝ {32+1.8×⍵} 0 100
32 212

```
```apl
      (⊢÷+/) 4 3 0 1     ⍝ {⍵÷+/⍵} 4 3 0 1
0.5 0.375 0 0.125

      ↓⍣2⊢2 2 2 2⍴⎕A     ⍝ (↓⍣2)2 2 2 2⍴⎕A
  AB  CD    EF  GH  
  IJ  KL    MN  OP  

```

When `⊢` is applied using reduction, the derived function selects the last sub-array of the array along the specified dimension. This is implemented as an idiom.

# Examples
```apl
      ⊢/1 2 3
3
      mat←↑'scent' 'canoe' 'arson' 'rouse' 'fleet'

      ⊢⌿mat  ⍝ last row                           
fleet
      ⊢/mat  ⍝ last column
tenet
 
      ⊢/[2]2 3 4⍴⍳24 ⍝ last row from each plane
 9 10 11 12
21 22 23 24
```
