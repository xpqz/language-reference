<div class="heading">
  <div class="name">Exponential</div>
  <div class="command">R←*Y</div>
</div>

`Y` must be numeric. `R` is numeric and is the `Y`th power of *e*, the base of natural logarithms.

# Example
```apl
      *1 0
2.718281828 1
 
      *0j1 1j2
0.5403023059J0.8414709848 ¯1.131204384J2.471726672
 
      1+*○0j1 ⍝ Euler Identity
0
```
