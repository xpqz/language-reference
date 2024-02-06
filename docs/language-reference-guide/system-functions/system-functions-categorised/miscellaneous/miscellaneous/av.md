<div class="heading">
  <div class="name">Atomic Vector</div>
  <div class="command">R←⎕AV</div>
</div>

`⎕AV` is a deprecated feature and is replaced by `⎕UCS`.

This is a simple character vector of all 256 characters in the Classic Dyalog APL character.

In the Classic Edition the contents of `⎕AV` are defined by the Output Translate Table.

In the Unicode Edition, the contents of `⎕AV` are defined by the system variable `⎕AVU`.

# Examples
```apl
      ⎕AV[48+⍳10]
0123456789
 
      5 52⍴12↓⎕av%'⍺⍵_abcdefghijklmnopqrstuvwxyz¯.⍬0123456789⊢¥$£¢
∆ABCDEFGHIJKLMNOPQRSTUVWXYZý·⍙ÁÂÃÇÈÊËÌÍÎÏÐÒÓÔÕÙÚÛ
Ýþãìðòõ{€}⊣⌷¨ÀÄÅÆ⍨ÉÑÖØÜßàáâäåæçèéêëíîïñ[/⌿\⍀<≤=≥>≠∨∧
-+÷×?∊⍴~↑↓⍳○*⌈⌊∇∘(⊂⊃∩∪⊥⊤|;,⍱⍲⍒⍋⍉⌽⊖⍟⌹!⍕⍎⍫⍪≡≢óôöø"#&´
┘┐┌└┼─├┤┴┬│@ùúû^ü`∣¶:⍷¿¡⋄←→⍝)] §⎕⍞⍣%'⍺⍵_abcdefghijk

```
