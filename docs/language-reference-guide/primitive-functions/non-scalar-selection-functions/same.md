<div class="heading">
  <div class="name">Same</div>
  <div class="command">R←⊣YR←⊢Y</div>
</div>

`Y` may be any array.

The result `R` is the argument `Y`.

# Examples
```apl
      ⊣'abc' 1 2 3
 abc  1 2 3
```
```apl
      (⊢,⎕size) 'a'⎕nl 4 ⍝ left tine of fork meaning "it"
acc      572
and      492
ascan    740
ascana   716
at      1764
avl    17476

```
