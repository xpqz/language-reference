<div class="heading">
  <div class="name">Conjugate</div>
  <div class="command">R←+Y</div>
</div>

If `Y` is complex, `R` is `Y` with the imaginary part of all elements negated.

If `Y` is real or non-numeric, `R` is the same array unchanged, although `⊣` is faster. See [Same on page 1](/same.md#Same).

# Examples
```apl
      +3j4
3J¯4
      +1j2 2j3 3j4
1J¯2 2J¯3 3J¯4
 
      3j4++3j4
6
      3j4×+3j4
25
 
      +A←⍳5
1 2 3 4 5
 
      +⎕EX'A'
1
```
