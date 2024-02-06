<div class="heading">
  <div class="name">State Indicator</div>
  <div class="command">R←⎕SI</div>
</div>

`R` is a nested vector of vectors giving the names of the functions or operators in the execution stack.

# Example
```apl

      )SI
#.PLUS[2]*
.
#.MATDIV[4]
#.FOO[1]*
⍎

      ⎕SI
 PLUS  MATDIV  FOO

      (⍴⎕LC)=⍴⎕SI
1
```

If execution stops in a callback function, `⎕DQ` will appear on the stack, and may occur more than once
```apl
      )SI
#.ERRFN[7]*
⎕DQ
#.CALC
⎕DQ
#.MAIN
```

To edit the function on the top of the stack:
```apl
      ⎕ED ⊃⎕SI
```

The name of the function which called this one:
```apl
      ⊃1↓⎕SI
```

To check if the function `∆N` is pendent:
```apl
     ((⊂∆N)∊1↓⎕SI)/'Warning : ',∆N,' is pendent'
```

See also ["Extended State Indicator: " on page 1](/xsi.md#ExtendedStateIndicator).
