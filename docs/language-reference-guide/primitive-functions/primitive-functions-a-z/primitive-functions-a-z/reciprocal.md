<div class="heading">
  <div class="name">Reciprocal</div>
  <div class="command">R←÷Y</div>
</div>

`Y` must be a numeric array.  `R` is numeric.  `R` is the reciprocal of `Y`; that is `1÷Y`.  If `⎕DIV=0`, `÷0` results in a `DOMAIN ERROR`.  If `⎕DIV=1`, `÷0` returns 0.

`⎕DIV` is an implicit argument of Reciprocal.

# Examples
```apl
      ÷4 2 5
0.25 0.5 0.2
 
      ÷0j1 0j¯1 2j2 4j4
0J¯1 0J1 0.25J¯0.25 0.125J¯0.125
 
      ⎕DIV←1 
      ÷0 0.5
0 2
```
