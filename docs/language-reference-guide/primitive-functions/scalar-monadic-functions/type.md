<div class="heading">
  <div class="name">Type</div>
  <div class="command">(⎕ML<1)</div>
</div>

Migration level must be such that `⎕ML<1` (otherwise `∊` means Enlist. See ["Enlist" on page 1](/enlist.md#Enlist)).

`Y` may be any array.  `R` is an array with the same shape and structure as `Y` in which a numeric value is replaced by 0 and a character value is replaced by `' '`.

# Examples
```apl
      ∊(2 3⍴⍳6)(1 4⍴'TEXT')
 0 0 0
 0 0 0
 
      ' '=∊'X'
1
```
