<div class="heading">
  <div class="name">Constant</div>
  <div class="command">R←{X}(A⍨)Y</div>
</div>

`A`,  `X` and `Y` are arrays. The Constant operator returns array `A`.

# Examples:
```apl

      'mu'⍨ 'any' ⎕NULL   ⍝ Always returns its operand
mu
      1E100 ('mu'⍨) 1j1
mu
      ¯1⍨¨ ⍳2 3
¯1 ¯1 ¯1
¯1 ¯1 ¯1

```
