<div class="heading">
  <div class="name">Enclose with Axes</div>
  <div class="command">R←⊂[K]Y</div>
</div>

`Y` may be any array.  `K` is a vector of zero or more axes of `Y`.  `R` is an array of the elements of `Y` enclosed along the axes `K`.  The shape of `R` is the shape of `Y` with the `K` axes removed:
```apl
      ⍴R ←→ (⍴Y)[(⍳⍴⍴R)~K]
```

The shape of each element of `R` is the shape of the `K`th axes of `Y`:
```apl
      ⍴⊃R ←→ (⍴Y)[,K]
```

# Examples
```apl
      ]display A←2 3 4⍴'DUCKSWANBIRDWORMCAKESEED'
┌┌→───┐
↓↓DUCK│
││SWAN│
││BIRD│
││    │
││WORM│
││CAKE│
││SEED│
└└────┘

```
```apl
      ]display ⊂[3]A
┌→─────────────────────┐
↓ ┌→───┐ ┌→───┐ ┌→───┐ │
│ │DUCK│ │SWAN│ │BIRD│ │
│ └────┘ └────┘ └────┘ │
│ ┌→───┐ ┌→───┐ ┌→───┐ │
│ │WORM│ │CAKE│ │SEED│ │
│ └────┘ └────┘ └────┘ │
└∊─────────────────────┘

```
```apl
      ]display ⊂[2 3]A
┌→──────────────┐
│ ┌→───┐ ┌→───┐ │
│ ↓DUCK│ ↓WORM│ │
│ │SWAN│ │CAKE│ │
│ │BIRD│ │SEED│ │
│ └────┘ └────┘ │
└∊──────────────┘
 
      ]display ⊂[1 3]A
┌→─────────────────────┐
│ ┌→───┐ ┌→───┐ ┌→───┐ │
│ ↓DUCK│ ↓SWAN│ ↓BIRD│ │
│ │WORM│ │CAKE│ │SEED│ │
│ └────┘ └────┘ └────┘ │
└∊─────────────────────┘
```
