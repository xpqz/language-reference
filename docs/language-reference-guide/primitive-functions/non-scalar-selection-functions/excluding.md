<div class="heading">
  <div class="name">Excluding</div>
  <div class="command">R←X~Y</div>
</div>

`X` must be a scalar or vector.  `R` is a vector of the elements of `X` excluding those elements which occur in `Y` taken in the order in which they occur in `X`.

Elements of `X` and `Y` are considered the same if `X≡Y` returns 1 for those elements.

`⎕CT` and `⎕DCT` are  implicit arguments of Excluding. Excluding is also known as Without.

# Examples
```apl
      'HELLO'~'GOODBYE'
HLL
      'MONDAY' 'TUESDAY' 'WEDNESDAY'~'TUESDAY' 'FRIDAY'
 MONDAY  WEDNESDAY
 
      5 10 15~⍳10
15
```
