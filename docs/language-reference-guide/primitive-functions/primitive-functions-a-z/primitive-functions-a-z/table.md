<div class="heading">
  <div class="name">Table</div>
  <div class="command">R←⍪Y</div>
</div>

`Y` may be any array. `R` is a 2-dimensional matrix of the elements of `Y` taken in row-major order, preserving the shape of the first dimension of `Y` if it exists

*Table* has been implemented according to the Extended APL Standard (*ISO/IEC 13751:2001).*

# Examples
```apl
      ]display {⍵ (⍴⍵)} ⍪'a'
┌→──────────┐
│ ┌→┐ ┌→──┐ │
│ ↓a│ │1 1│ │
│ └─┘ └~──┘ │
└∊──────────┘
 
      ]display {⍵ (⍴⍵)} ⍪'hello'
┌→──────────┐
│ ┌→┐ ┌→──┐ │
│ ↓h│ │5 1│ │
│ │e│ └~──┘ │
│ │l│       │
│ │l│       │
│ │o│       │
│ └─┘       │
└∊──────────┘
 
      ]display {⍵ (⍴⍵)} ⍪2 3 4⍴⍳24
┌→─────────────────────────────────────────────┐
│ ┌→──────────────────────────────────┐ ┌→───┐ │
│ ↓ 1  2  3  4  5  6  7  8  9 10 11 12│ │2 12│ │
│ │13 14 15 16 17 18 19 20 21 22 23 24│ └~───┘ │
│ └~──────────────────────────────────┘        │
└∊─────────────────────────────────────────────┘
```
