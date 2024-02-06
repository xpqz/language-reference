<div class="heading">
  <div class="name">Extended State Indicator</div>
  <div class="command">R←⎕XSI</div>
</div>

`R` is a nested vector of character vectors giving the full path names of the functions or operators in the execution stack. Note that if a function has changed space, its original (home) space is reported, rather than its current one.

# Example

In the following, function `foo` in namespace `x` has called `goo` in namespace `y`.  Function `goo` has then changed space (`⎕CS`) to namespace `z` where it has been suspended:
```apl
 
      )si
[z] y.goo[2]*
x.foo[1]
 
```

`⎕XSI` reports the full path name of each function:
```apl
       ⎕xsi
 #.y.goo  #.x.foo
```

This can be used for example, to edit all functions in the stack, irrespective of the current namespace by typing:    `⎕ed ⎕xsi`

See also ["State Indicator: " on page 1](/si.md#StateIndicator).
