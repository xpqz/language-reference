<div class="heading">
  <div class="name">Token Requests</div>
  <div class="command">R←⎕TREQ Y</div>
</div>

`Y` is a simple scalar or vector of thread numbers.

`R` is a vector containing the concatenated token requests for all the threads specified in `Y`. This is effectively the result of catenating all of the right arguments together for all threads in `Y` that are currently executing `⎕TGET`.

# Example
```apl
    ⎕TREQ ⎕TNUMS    ⍝ tokens required by all threads.
```
