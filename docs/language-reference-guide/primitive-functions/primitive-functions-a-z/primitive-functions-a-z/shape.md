<div class="heading">
  <div class="name">Shape</div>
  <div class="command">R←⍴Y</div>
</div>

`Y` may be any array.  `R` is a non-negative integer vector whose elements are the dimensions of `Y`.  If `Y` is a scalar, then `R` is an empty vector.  The rank of `Y` is given by `⍴⍴Y`.

# Examples
```apl
      ⍴10
 
      ⍴'CAT'
3
 
      ⍴3 4⍴⍳12
3 4
 
      +G←(2 3⍴⍳6)('CAT' 'MOUSE' 'FLEA')
 1 2 3   CAT  MOUSE  FLEA
 4 5 6
 
      ⍴G
2
 
      ⍴⍴G
1
 
      ⍴¨G
 2 3  3
 
      ⍴¨¨G
          3  5  4
```
