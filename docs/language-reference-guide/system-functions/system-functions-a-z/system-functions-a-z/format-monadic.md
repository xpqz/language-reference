<div class="heading">
  <div class="name">Format (Monadic)</div>
  <div class="command">R←⎕FMT Y</div>
</div>

`Y` may be any array.  `R` is a simple character matrix which appears the same as the default display of `Y`.  If `Y` contains control characters from `⎕TC`, they will be resolved.

# Examples
```apl
      A←⎕FMT '∩' ,⎕TC[1],'∘'
 
      ⍴A
1 1
      A
⍝
 
      A←⎕VR 'FOO'
 
      A
     ∇ R←FOO
[1]    R←10
     ∇
 
      ⍴A
31
      B←⎕FMT A
 
      B
     ∇ R←FOO
[1]    R←10
     ∇
 
      ⍴B
3 12
```
