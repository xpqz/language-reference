<div class="heading">
  <div class="name">Query Stop</div>
  <div class="command">R←⎕STOP Y</div>
</div>

`Y` must be a simple character scalar or vector which is taken to be the name of a visible defined function or operator.  `R` is a simple non-negative integer vector of the line numbers of the function or operator named by `Y` on which stop controls are set, shown in ascending order.  The value 0 in `R` indicates that a stop control is set immediately prior to exit from the function or operator.

# Example
```apl
      ⎕STOP'FOO'
0 1
```
