<div class="heading">
  <div class="name">Comparison Tolerance</div>
  <div class="command">⎕CT</div>
</div>

The value of `⎕CT` determines the precision with which two numbers are judged to be equal.  Two numbers, `X` and `Y`, are judged to be equal if `(|X-Y)≤⎕CT×(|X)⌈|Y`where `≤` is applied without tolerance.

Thus `⎕CT` is not used as an absolute value in comparisons, but rather specifies a relative value that is dependent on the magnitude of the number with the greater magnitude. It then follows that `⎕CT` has no effect when either of the numbers is zero.

`⎕CT` may be assigned any value in the range from `0` to  `2*¯32`  (about `2.3E¯10`). A value of `0` ensures exact comparison.  The value in a clear workspace is `1E¯14`. `⎕CT` has Namespace scope.

If `⎕FR` is 1287, the system uses `⎕DCT`. See [Decimal Comparison Tolerance  on page 1](/dct.md#DecimalComparisonTolerance).

# Examples
```apl
      ⎕CT←1E¯10
      1.00000000001 1.0000001 = 1
1 0
```
