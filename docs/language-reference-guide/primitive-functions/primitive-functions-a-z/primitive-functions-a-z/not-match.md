<div class="heading">
  <div class="name">Not Match</div>
  <div class="command">R←X≢Y</div>
</div>

`Y`may be any array.  `X` may be any array.  `R` is a simple Boolean scalar.  If `X` is identical to `Y`, then `R` is 0.  Otherwise `R` is 1.

Non-empty arrays are identical if they have the same structure and the same values in all corresponding locations.  Empty arrays are identical if they have the same shape and the same prototype (disclosed nested structure).

`⎕CT` and `⎕DCT` are  implicit arguments of Not Match.

# Examples
```apl
      ⍬≢⍳0
0
      ''≢⍳0
1
```
```apl

      ⊢A←⊂(⍳3) 'ABC'
  1 2 3  ABC
```
```apl

      A≢(⍳3)'ABC'
1
      A≢⊂(⍳3) 'ABC'
0
      ⍬≢0⍴A
1
      (1↑0⍴A)≢⊂(0 0 0) '   '
1
```
