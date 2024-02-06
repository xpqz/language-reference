<div class="heading">
  <div class="name">Magnitude</div>
  <div class="command">R←|Y</div>
</div>

`Y` may be any numeric array. `R` is numeric composed of the absolute (unsigned) values of `Y`.

Note that the magnitude of a complex number (a+ib) is defined to be a2+b2

# Examples
```apl
      |2 ¯3.4 0 ¯2.7
2 3.4 0 2.7
 
      |3j4
5
```

`⎕IO` is an implicit argument of magnitude.
