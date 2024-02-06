<div class="heading">
  <div class="name">Roll</div>
  <div class="command">R←?Y</div>
</div>

`Y` may be any non-negative integer array. `R` has the same shape as `Y` at each depth.

For each positive element of `Y` the corresponding element of `R` is an integer, pseudo-randomly selected from the integers `⍳Y` with each integer in this population having an equal chance of being selected.

For each zero element of `Y`, the corresponding element of `R` is a pseudo-random floating-point value in the range 0 - 1, but excluding 0 and 1, i.e. `(0<R[I]<1)`.

`⎕IO` and `⎕RL` are implicit arguments of Roll. A side effect of Roll is to change the value of `⎕RL`.

Note that different random number generators are available; see `⎕RL` for more information.

# Examples
```apl

      ?9 9 9
2 7 5
      ?3⍴0
0.3205466592 0.3772891947 0.5456603511

```
