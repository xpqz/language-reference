<div class="heading">
  <div class="name">Split</div>
  <div class="command">R←↓[K]Y</div>
</div>

`Y` may be any array.  The axis specification is optional.  If present, `K` must be a simple integer scalar or one-element vector.  The value of `K` must be an axis of `Y`.  If absent, the last axis is implied.

The items of `R` are the sub-arrays of `Y` along the `K`th axis.  `R` is a scalar if `Y` is a scalar.  Otherwise `R` is an array whose rank is`¯1+⍴⍴Y` and whose shape is `(K≠⍳⍴⍴Y)/⍴Y`.

# Examples
```apl
      ↓3 4⍴'MINDTHATSTEP'
 MIND  THAT  STEP
 
      ↓2 5⍴⍳10
 1 2 3 4 5  6 7 8 9 10
 
      ↓[1]2 5⍴⍳10
 1 6  2 7  3 8  4 9  5 10
```
