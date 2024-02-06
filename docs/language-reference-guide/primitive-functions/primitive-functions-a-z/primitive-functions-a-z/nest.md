<div class="heading">
  <div class="name">Nest</div>
  <div class="command">R←⊆Y</div>
</div>

Classic Edition:  the symbol `⊆` (Left Shoe Underbar) is not available in Classic Edition, and Nest is instead represented by `⎕U2286`.

`Y` may be any array.

If `Y` is simple, `R` is a scalar array whose item is the array `Y`.  If `Y` is a simple scalar or is already nested, `R` is `Y` unchanged.

# Examples
```apl
      ⊆1 2 3
┌─────┐
│1 2 3│
└─────┘
      ⊆ 1 (1 2 3)
┌─┬─────┐
│1│1 2 3│
└─┴─────┘
      ⊆'Dyalog'
┌──────┐
│Dyalog│
└──────┘
      ⊆'Dyalog' 'APL'
┌──────┬───┐
│Dyalog│APL│
└──────┴───┘

```
