<div class="heading">
  <div class="name">Called Monadically</div>
  <div class="command">R←900⌶Y</div>
</div>

Identifies how the current function was called. `900⌶` applies only when called from within a variadic defined function (not a dfn).

`Y` may be any array.

The result `R` is Boolean. 1 means that the current function was called monadically; 0 means that it wasn't. If there is no function on the stack, the result is 0.

# Example
```apl
     ∇ r←{left}foo right
[1]    r←900⌶⍬
     ∇
      foo 10
1
      0 foo 10
0

```
