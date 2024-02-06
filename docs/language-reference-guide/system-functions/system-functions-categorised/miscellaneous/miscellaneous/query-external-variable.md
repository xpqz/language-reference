<div class="heading">
  <div class="name">Query External Variable</div>
  <div class="command">R←⎕XT Y</div>
</div>

`Y` must be a simple character scalar or vector which is taken to be a variable name.  `R` is a simple character vector containing the file reference of the external array associated with the variable named by `Y`, or the null vector if there is no associated external array.

# Example
```apl
      ⎕XT'V'
EXT\ARRAY
 
      ⍴⎕XT'G'
0
 
```
