<div class="heading">
  <div class="name">Kill Thread</div>
  <div class="command">{R}←{X}⎕TKILL Y</div>
</div>

`Y` must be a simple array of integers representing thread numbers to be terminated. `X` is a Boolean single, defaulting to 1, which indicates that all descendant threads should also be terminated.

The shy result `R` is a vector of the numbers of all threads that have been terminated.

The base thread 0 is always excluded from the cull.

# Examples
```apl
      ⎕TKILL 0            ⍝ Kill background threads.
 
      ⎕TKILL ⎕TID         ⍝ Kill self and descendants.
 
      0 ⎕TKILL ⎕TID       ⍝ Kill self only.
 
      ⎕TKILL ⎕TCNUMS ⎕TID ⍝ Kill descendants.
```
