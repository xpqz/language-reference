<div class="heading">
  <div class="name">Decimal Comparison Tolerance</div>
  <div class="command">⎕DCT</div>
</div>

The value of `⎕DCT` determines the precision with which two numbers are judged to be equal when the value of `⎕FR` is 1287. If `⎕FR` is 645, the system uses `⎕CT`.

`⎕DCT` may be assigned any value in the range from `0` to `2*¯32` (about `2.3283064365386962890625E¯10`). A value of `0` ensures exact comparison. The value in a clear workspace is `1E¯28`. `⎕DCT` has Namespace scope.

For further information, see ["Comparison Tolerance: " on page 1](/ct.md#ComparisonTolerance).

# Examples
```apl
      ⎕DCT←1E¯10
      1.00000000001 1.0000001 = 1
1 0
```
