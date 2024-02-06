<div class="heading">
  <div class="name">Disclose</div>
  <div class="command">(⎕ML)</div>
</div>

The symbol chosen to represent Disclose depends on the current Migration Level.

If  `⎕ML<2`, Disclose is represented by the symbol: `⊃`.

If  `⎕ML≥2`, Disclose is represented by the symbol: `↑`.

`Y` may be any array.  `R` is an array.  If `Y` is non-empty, `R` is the value of the first item of `Y` taken in ravel order.  If `Y` is empty, `R` is the prototype of `Y`.

Disclose is the inverse of Enclose.  The identity `R←→⊃⊂R` holds for all `R`.  Disclose is also referred to as First.

# Examples
```apl
      ⊃1
1
 
      ⊃2 4 6
2
 
      ⊃'MONDAY' 'TUESDAY'
MONDAY
 
      ⊃(1 (2 3))(4 (5 6))
1  2 3
 
      ⊃⍳0
0
 
      ' '=⊃''
1
 
      ⊃1↓⊂1,⊂2 3
0  0 0
```
