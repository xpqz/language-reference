<div class="heading">
  <div class="name">Space Indicator</div>
  <div class="command">R←⎕RSI</div>
</div>

`R` is a vector of refs to the spaces from which functions in the state indicator were called `(⍴⎕RSI←→⍴ ⎕NSI ←→⍴⎕SI)`.

`⎕RSI` and `⎕ NSI` are identical except that `⎕RSI` returns refs to the spaces whereas `⎕NSI` returns their names. Put another way: `⎕NSI ←→⍕¨⎕RSI``.`

Note that`⎕RSI` returns refs to the spaces *from which* functions were called not those *in which* they are currently running.

# Example
```apl
      )OBJECTS
xx      yy
 
      ⎕VR 'yy.foo'
     ∇ r←foo
[1]    r←⎕SE.goo
     ∇                          
      ⎕VR'⎕SE.goo'
     ∇ r←goo
[1]    r←⎕SI,[1.5]⎕RSI
     ∇
 
      )CS xx
#.xx
      calling←#.yy.foo
      ]display calling
┌→───────────┐
↓ ┌→──┐      │
│ │goo│ #.yy │
│ └───┘      │
│ ┌→──┐      │
│ │foo│ #.xx │
│ └───┘      │
└∊───────────┘
```
