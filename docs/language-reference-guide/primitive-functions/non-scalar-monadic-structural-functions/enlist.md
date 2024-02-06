<div class="heading">
  <div class="name">Enlist</div>
  <div class="command">(⎕ML≥1)</div>
</div>

Migration level must be such that `⎕ML≥1` (otherwise see ["Type" on page 1](/type.md#Type)).

`Y` may be any array, `R` is a simple vector created from all the elements of `Y` in ravel order.

# Examples
```apl

      ⎕ML←1         ⍝  Migration level 1
      MAT←2 2⍴'MISS' 'IS' 'SIP' 'PI' ⋄ MAT
 MISS  IS
 SIP   PI
      ∊MAT
MISSISSIPPI
 
      M←1 (2 2⍴2 3 4 5) (6(7 8))
      M
1  2 3  6  7 8
   4 5
      ∊M
1 2 3 4 5 6 7 8
```
