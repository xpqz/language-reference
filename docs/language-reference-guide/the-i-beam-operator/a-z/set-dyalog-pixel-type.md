<div class="heading">
  <div class="name">Set Dyalog Pixel Type</div>
  <div class="command">R←2035⌶Y</div>
</div>

Determines how Coord `'Pixel'` is interpreted. This is determined initially by the value of the DYALOG_PIXEL_TYPE parameter and, when altered by this function,  applies to all subsequent GUI operations.

`Y` is a character vector that is either `'ScaledPixel'` or `'RealPixel'`. Any other value will cause a `DOMAIN ERROR`.

The result `R` is the previous value.

# Example
```apl
      2035⌶'ScaledPixel'
RealPixel
      2035⌶'RealPixel'
ScaledPixel

      2035⌶'realpixel'
DOMAIN ERROR
      2035⌶'realpixel'
     ∧

```
