# Mixed Functions

Mixed rank functions and special symbols are summarised in [Table 1](/#MixedRankFunctions). For convenience, they are sub-divided into five classes:

Mixed rank functions and special symbols

| Structural | These functions change the structure of the arguments in some way. |
| --- | --- |
| Selection | These functions select elements from an argument. |
| Selector | These functions identify specific elements by a Boolean map or by an ordered set of indices. |
| Miscellaneous | These functions transform arguments in some way, or provide information about the arguments. |
| Special | These symbols have special properties. |

In general, the structure of the result of a mixed primitive function is different from that of its arguments.

Scalar extension may apply to some, but not all, dyadic mixed functions.

Mixed primitive functions are not pervasive. The function is applied to elements of the arguments, not necessarily independently.

### Examples
```apl
      'CAT' 'DOG' 'MOUSE'⍳⊂'DOG'
2 
      3↑ 1 'TWO' 3 'FOUR'
1  TWO  3
```

In the following tables, note that:

- `[]` Implies axis specification is optional
- $  This function is in another class

Structural Primitive Functions

| Symbol | Monadic | Dyadic |
| --- | --- | --- |
| `⍴` | $ | [Reshape](/reshape.md#) |
| `,` | [Ravel ](/ravel.md#) `[]` | [Catenate/Laminate](/catenate-laminate.md#) `[]` |
| `⍪` | [Table](/table.md#) | [Catenate First / Laminate ](/catenate-first.md#) `[]` |
| `⌽` | [Reverse ](/reverse.md#) `[]` | [Rotate ](/rotate.md#) `[]` |
| `⊖` | [Reverse First ](/reverse-first.md#) `[]` | [Rotate First ](/rotate-first.md#) `[]` |
| `⍉` | [Transpose](/transpose-monadic.md#) | [Transpose](/transpose-dyadic.md#) |
| `↑` | [Mix](/mix.md#) / [Disclose ](/disclose.md#) `[]` | $ |
| `↓` | [Split ](/split.md#) `[]` | $ |
| `⊂` | [Enclose ](/enclose.md#) `[]` | [Partitioned Enclose ](/partitioned-enclose.md#) `[]` |
| `⊆` | [Nest](/nest.md#) | [Partition ](/partition.md#) `[]` |
| `∊` | [Enlist](/enlist.md#) (See [Type](/type.md#) ) | $ |

Selection Primitive Functions

| Symbol | Monadic | Dyadic |
| --- | --- | --- |
| `⊃` | [Disclose ](/disclose.md#) / [Mix](/mix.md#) | [Pick](/pick.md#) |
| `↑` | $ | [Take ](/take.md#) `[]` |
| `↓` | $ | [Drop ](/drop.md#) `[]` |
| `/` |  | [Replicate ](/replicate.md#) `[]` |
| `⌿` |  | [Replicate First ](/replicate-first.md#) `[]` |
| `\` |  | [Expand ](/expand.md#) `[]` |
| `⍀` |  | [Expand First ](/expand-first.md#) `[]` |
| `~` | $ | [Without (Excluding)](/excluding.md#) |
| `∩` |  | [Intersection](/intersection.md#) |
| `∪` | [Unique](/unique.md#) | [Union](/union.md#) |
| `⊣` | [Same](/same.md#) | [Left](/left.md#) |
| `⊢` | [Same](/same.md#) | [Right](/right.md#) |
| `⌷` | [Materialise](/materialise.md#) | [Index](/index.md#) |
| `≠` | [Unique Mask](/unique-mask.md#) |  |

Selector Primitive Functions

| Symbol | Monadic | Dyadic |
| --- | --- | --- |
| `⍳` | [Index Generator](/index-generator.md#) | [Index Of](/index-of.md#) |
| `⍸` | [Where](/where.md#) | [Interval Index](/interval-index.md#) |
| `∊` | $ | [Membership](/membership.md#) |
| `⍋` | [Grade Up](/grade-up-monadic.md#) | [Grade Up](/grade-up-dyadic.md#) |
| `⍒` | [Grade Down](/grade-down-monadic.md#) | [Grade Down](/grade-down-dyadic.md#) |
| `?` | $ | [Deal](/deal.md#) |
| `⍷` |  | [Find](/find.md#) |

Miscellaneous Primitive Functions

| Symbol | Monadic | Dyadic |
| --- | --- | --- |
| `⍴` | [Shape](/shape.md#) | $ |
| `≡` | [Depth](/depth.md#) | [Match](/match.md#) |
| `≢` | [Tally](/tally.md#) | [Not Match](/not-match.md#) |
| `⍎` | [Execute](/execute.md#) | [Execute](/execute.md#) |
| `⍕` | [Format](/format-monadic.md#) | [Format](/format-dyadic.md#) |
| `⊥` |  | [Decode (Base)](/decode.md#) |
| `⊤` |  | [Encode (Representation)](/encode.md#) |
| `⌹` | [Matrix Inverse](/matrix-inverse.md#) | [Matrix Divide](/matrix-divide.md#) |

Special Syntax

| Symbol | Monadic | Dyadic |
| --- | --- | --- |
| `→` | [Abort](/abort.md#) |  |
| `→` | [Branch](/branch.md#) |  |
| `←` |  | [Assignment](/assignment.md#) |
| `[I]←` |  | [Assignment(Indexed)](/assignment-indexed.md#) |
| `(I)←` |  | [Assignment(Selective)](/assignment-selective.md#) |
| `[]` |  | [Indexing](/indexing.md#) |
