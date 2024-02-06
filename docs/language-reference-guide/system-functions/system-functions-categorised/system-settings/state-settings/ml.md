<div class="heading">
  <div class="name">Migration Level</div>
  <div class="command">⎕ML</div>
</div>

`⎕ML` determines the degree of migration of the Dyalog APL language towards IBM's APL2.  Setting this variable to other than its default value of `1` changes the interpretation of certain symbols and language constructs. `⎕ML` has Namespace scope.

| `⎕ML←0` | `` | Original Native Dyalog |
| --- | --- | --- |
| `⎕ML←1` | `Z←∊R` | Monadic `'∊'` is interpreted as 'enlist' rather than 'type'. |
| `⎕ML←2` | `Z←↑R` | Monadic `'↑'` is interpreted as 'first' rather than 'mix'. |
| `` | `Z←⊃R` | Monadic `'⊃'` is interpreted as 'mix' rather than 'first'. |
| `` | `Z←≡R` | Monadic `'≡'` returns a positive rather than a negative value, if its argument has non-uniform depth. |
| `⎕ML←3` | `R←X⊂[K]Y` | Dyadic `'⊂'` follows the APL2 (rather than the original Dyalog APL) convention. |
| `` | `⎕TC` | The order of the elements of `⎕TC` is the same as in APL2. |

Subsequent versions of Dyalog APL may provide further migration levels.

# Examples
```apl
      X←2(3 4)

      ⎕ML←0
      ∊X
0  0 0
      ↑X
2 0
3 4
      ⊃X
2
      ≡X
¯2

```
```apl

      ⎕ML←1
      ∊X
2 3 4
      ↑X
2 0
3 4
      ⊃X
2
      ≡X
¯2

```
```apl

      ⎕ML←2
      ∊X
2 3 4
      ↑X
2
      ⊃X
2 0
3 4
      ≡X
2

```
