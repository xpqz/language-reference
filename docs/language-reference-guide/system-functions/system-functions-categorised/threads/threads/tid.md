<div class="heading">
  <div class="name">Current Thread Identity</div>
  <div class="command">R←⎕TID</div>
</div>

`R` is a simple integer scalar whose value is the number of the current thread.

# Examples
```apl
      ⎕TID     ⍝ Base thread number
0
 
      ⍎&'⎕TID' ⍝ Thread number of async ⍎.
1
```
