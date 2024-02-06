<div class="heading">
  <div class="name">Thread Child Numbers</div>
  <div class="command">R←⎕TCNUMS Y</div>
</div>

`Y` must be a simple array of integers representing thread numbers.

The result `R` is a simple integer vector of the child threads of each thread of `Y`.

# Examples
```apl
      ⎕TCNUMS 0
2 3
 
      ⎕TCNUMS 2 3
4 5 6 7 8 9
```
