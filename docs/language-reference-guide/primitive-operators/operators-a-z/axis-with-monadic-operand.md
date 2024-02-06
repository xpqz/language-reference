<div class="heading">
  <div class="name">Axis (with Monadic Operand)</div>
  <div class="command">R←f[B]Y</div>
</div>

`f` must be a monadic primitive mixed function taken from those shown in [Table 1](/#MonadicMixed) below, or a function derived from the operators Reduction (`/`) or Scan (`\`). `B` must be a numeric scalar or vector. `Y` may be any array whose items are appropriate to function `f`. Axis does not follow the normal syntax of an operator.

Primitive monadic mixed functions with optional axis.

| Function | Name | Range of B |
| --- | --- | --- |
| `⌽ or ⊖` | Reverse | `B∊⍳⍴⍴Y` |
| `↑` | Mix | `(0≠1|B)^(B>⎕IO-1)^(B<⎕IO+⍴⍴Y)` |
| `↓` | Split | `B∊⍳⍴⍴Y` |
| `,` | Ravel | fraction, or zero or more axes of `Y` |
| `⊂` | Enclose | `(B≡⍳0)∨(^/B∊⍳⍴⍴Y)` |

In most cases, `B` must be an integer which identifies a specific axis of `Y`. However, when  `f` is the Mix function (`↑`),   `B` is a fractional value whose lower and upper integer bounds select an adjacent pair of axes of `Y` or an extreme axis of `Y`.

For Ravel (`,`) and Enclose (`⊂`), `B` can be a vector of two or more axes.

`⎕IO` is an implicit argument of the derived function which determines the meaning of `B`.

# Examples
```apl
      ⌽[1]2 3⍴⍳6
4 5 6
1 2 3
 
      ↑[.1]'ONE' 'TWO'
OT
NW
EO
```
