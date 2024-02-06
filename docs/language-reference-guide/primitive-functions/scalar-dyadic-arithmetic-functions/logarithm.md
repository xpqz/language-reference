<div class="heading">
  <div class="name">Logarithm</div>
  <div class="command">R←X⍟Y</div>
</div>

`X` and `Y` must be numeric arrays. `X` cannot be 1 unless `Y` is also 1. `R` is the base `X` logarithm of `Y`.

Note that Logarithm (dyadic `⍟`) is defined in terms of Natural Logarithm (monadic `⍟`) as:
```apl
      X⍟Y←→(⍟Y)÷⍟X
```

# Examples
```apl
      10⍟100 2
2 0.3010299957
 
      2 10⍟0J1 1J2
0J2.266180071 0.3494850022J0.4808285788
 
      1 ⍟ 1
1
      2 ⍟ 1
0
```
