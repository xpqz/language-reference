<div class="heading">
  <div class="name">Reduce</div>
  <div class="command">R←f/[K]Y</div>
</div>

`f` must be a dyadic function.  `Y` may be any array whose items in the sub-arrays along the `K`th axis are appropriate to function `f`.

The axis specification is optional.  If present, `K` must identify an axis of `Y`.  If absent, the last axis of `Y` is implied.  The form `R←f⌿Y` implies the first axis of `Y`.

`R` is an array formed by applying function `f` between items of the vectors along the `K`th (or implied) axis of `Y`. For a typical vector `Y`, the result `R` is:
```apl
       R  ←→ ⊂(1⊃Y)f(2⊃Y)f......f(n⊃Y)
```

The shape `S` of `R` is the shape of `Y` excluding the `K`th axis, i.e.
```apl
       S  ←→  ⍴R  ←→  (K≠⍳⍴⍴Y)/⍴Y
```

If `Y` is a scalar then for any function `f`, `R` is `Y`.

If the length of the `K`th axis of `Y` is 1, or if the length of any other axis of `Y` is 0, then `f` is not applied and `R` is `S⍴Y`.

Otherwise, if the length of the `K`th axis is 0 then the result depends on `f` and on `⊃Y` (the prototypical item of `Y`) as follows:

If `f` is one of the functions listed in [Table 1](/#IdentityElements) then `R` is `S⍴⊂I`, where `I` is formed from `⊃Y` by replacing each depth-zero item of `⊃Y` with the **identity element** from the table.

Otherwise if `f` is Catenate, `R` is `S⍴⊂0/⊃Y`. If `f` is Catenate First, `R` is `S⍴⊂0⌿⊃Y`. If `f` is Catenate along the Jth axis, `R` is `S⍴⊂0/[J]⊃Y`. See [Catenate/Laminate on page 1](/primitive-functions/catenate-laminate.md#Catenate/Laminate).

Otherwise, `DOMAIN ERROR` is reported.

Identity Elements

| Function |  | Identity |
| --- | --- | --- |
| Add | `+` | `0` |
| Subtract | `-` | `0` |
| Multiply | `×` | `1` |
| Divide | `÷` | `1` |
| Residue | `|` | `0` |
| Minimum | `⌊` | `M M represents the largest representable value: typically this is 1.7E308, unless ⎕FR is 1287, when the value is 1E6145.` |
| Maximum | `⌈` | `-M` |
| Power | `*` | `1` |
| Binomial | `!` | `1` |
| And | `∧` | `1` |
| Or | `∨` | `0` |
| Less | `<` | `0` |
| Less or Equal | `≤` | `1` |
| Equal | `=` | `1` |
| Greater | `>` | `0` |
| Greater or Equal | `≥` | `1` |
| Not Equal | `≠` | `0` |
| Encode | `⊤` | `0` |
| Union | `∪` | `⍬` |
| Replicate | `/⌿` | `1` |
| Expand | `\⍀` | `1` |
| Rotate | `⌽⊖` | `0` |

# Examples
```apl
      ∨/0 0 1 0 0 1 0
1
      MAT
1 2 3
4 5 6
 
      +/MAT
6 15
 

```
```apl
      +⌿MAT
5 7 9
 
      +/[1]MAT
5 7 9
 
      +/(1 2 3)(4 5 6)(7 8 9)
 12 15 18
 
      ,/'ONE' 'NESS'
 ONENESS
 
      +/⍳0
0
```
```apl
      (⊂⍬)≡,/⍬ 
1
      (⊂'')≡,/0⍴'Hello' 'World' 
1
      (⊂0 3 4⍴0)≡⍪/0⍴⊂2 3 4⍴0
1
```
