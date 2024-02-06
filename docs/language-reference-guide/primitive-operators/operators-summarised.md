# Operators Summarised

[Table 1](/#MonadicOperators) and [Table 1](/#DyadicOperators) below summarise the Monadic and Dyadic primitive operators whose detailed descriptions  follow in alphabetical order in this section.

Some operators may include an axis specification (indicated `[]`in the tables). Note that in these case `⎕IO` is an implicit argument of the derived function.

Monadic Primitive Operators

| Name | Producing Monadic derived function | Producing Dyadic derived function |
| --- | --- | --- |
| Assignment (Modified) |  | `Xf←Y` |
| Assignment (Indexed Modified) |  | `X[I]f←Y` |
| Assignment (Selective Modified) |  | `(EXP X)f←Y` |
| Commute | `f⍨Y` | `Xf⍨Y` |
| Each | `f¨Y` | `Xf¨Y` |
| I-Beam | `A⌶Y` | `X(A⌶)Y` |
| Key | `f⌸Y` | `Xf⌸Y` |
| Reduction | `f/Y  [ ]` | `Xf/Y [ ]` |
| Reduction First | `f⌿Y  [ ]` | `Xf⌿Y [ ]` |
| Scan | `f\Y  [ ]` | `` |
| Scan First | `f⍀Y  [ ]` | `` |
| Spawn | `f&Y` | `Xf&Y` |

Dyadic Primitive Operators

| Name | Producing Monadic derived function | Producing Dyadic derived function |
| --- | --- | --- |
| At | `f@gY` | `Xf@gY` |
| Atop | `f⍤gY` | `Xf⍤gY` |
| Axis | `f[B]Y` | `Xf[B]Y` |
| Beside | `f∘gY` | `Xf∘gY` |
| Bind | `A∘gY` | `` |
| `(f∘B)Y` | `` |
| Constant | `(A⍨)Y` | `X(A⍨)Y` |
| Inner Product | `` | `Xf.gY` |
| Outer Product | `` | `X∘.gY` |
| Over | `f⍥gY` | `Xf⍥gY` |
| Power | `f⍣gY` | `Xf⍣gY` |
| Rank | `f⍤kY` | `Xf⍤kY` |
| Stencil | `f⌺gY` | `` |
| Variant | `f⍠gY` | `Xf⍠gY` |
