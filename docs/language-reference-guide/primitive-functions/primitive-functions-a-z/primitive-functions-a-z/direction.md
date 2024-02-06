<div class="heading">
  <div class="name">Direction (Signum)</div>
  <div class="command">R←×Y</div>
</div>

`Y` may be any numeric array.

Where an element of `Y` is real, the corresponding element of `R` is an integer whose value indicates whether the value is negative (`¯1`), zero (`0`) or positive (`1`).

Where an element of `Y` is complex, the corresponding element of `R` is a number with the same phase but with magnitude (absolute value) 1. It is equivalent to `Y÷|Y`.

# Examples
```apl
      ×¯15.3 0 101
¯1 0 1
 
      ×3j4 4j5
0.6J0.8 0.6246950476J0.7808688094
 
      {⍵÷|⍵}3j4 4j5
0.6J0.8 0.6246950476J0.7808688094
 
      |×3j4 4j5
1 1
```
