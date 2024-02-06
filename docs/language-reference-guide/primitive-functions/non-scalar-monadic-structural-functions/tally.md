<div class="heading">
  <div class="name">Tally</div>
  <div class="command">R←≢Y</div>
</div>

`Y` may be any array.  `R` is a simple numeric scalar.

Tally returns the number of major cells of `Y`. See Cells and Subarrays["Cells and Sub-arrays" on page 1](/introduction/variables/cells-and-subarrays.md#CellsSubarrays).

This can also be expressed as the length of the leading axis or 1 if `Y` is a scalar. Tally is equivalent to the function `{⍬⍴(⍴⍵),1}`.

# Examples
```apl
      ≢2 3 4⍴⍳10
2
      ≢2
1
      ≢⍬
0
```

Note that `≢V` is useful for returning the length of vector `V` as a scalar.  (In contrast, `⍴V` is a one-element vector.)
