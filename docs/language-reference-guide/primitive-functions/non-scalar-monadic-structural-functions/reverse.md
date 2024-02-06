<div class="heading">
  <div class="name">Reverse</div>
  <div class="command">R←⌽[K]Y</div>
</div>

`Y` may be any array.  The axis specification is optional.  If present, `K` must be an integer scalar or one-element vector.  The value of `K` must be an axis of `Y`.  If absent, the last axis is implied.  The form `R←⊖Y` implies the first axis.

`R` is the array `Y` reversed on the `K`th or implied axis.

# Examples
```apl
      ⌽1 2 3 4 5
5 4 3 2 1
 
      M
1 2 3
4 5 6
      ⌽M
3 2 1
6 5 4
      ⊖M
4 5 6
1 2 3
      ⌽[1]M
4 5 6
1 2 3
```
