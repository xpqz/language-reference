<div class="heading">
  <div class="name">Abort</div>
  <div class="command">→</div>
</div>

This is a special case of the Branch function used in the niladic sense.  If it occurs in a statement it must be the only symbol in an expression or the only symbol forming an expression in a text string to be executed by `⍎`.  It clears the most recently suspended statement and all of its pendent statements from the state indicator.

The Abort function has no explicit result.  The function is not in the function domain of operators.

# Examples
```apl
      ∇ F
[1]    'F[1]'
[2]    G
[3]    'F[3]'
      ∇
 
      ∇ G
[1]    'G[1]'
[2]    →
[3]    'G[3]'
      ∇
 
      F
F[1]
G[1]
 
      ⎕VR'VALIDATE'
     ∇ VALIDATE
 [1]   →(12=1↑⎕AI)⍴0 ⋄ 'ACCOUNT NOT AUTHORISED' ⋄ →
     ∇
 
      VALIDATE
ACCOUNT NOT AUTHORISED
 
      1↑⎕AI
52
```
