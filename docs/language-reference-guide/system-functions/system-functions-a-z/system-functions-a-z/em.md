<div class="heading">
  <div class="name">Event Message</div>
  <div class="command">R←⎕EM Y</div>
</div>

`Y` must be a simple non-negative integer scalar or vector of event codes.  If `Y` is a scalar, `R` is a simple character vector containing the associated event message.  If `Y` is a vector, `R` is a vector of character vectors containing the corresponding event messages.

If `Y` refers to an undefined error code "`n`", the event message returned is "`ERROR NUMBER n`".

# Example
```apl
      ⎕EM 11
DOMAIN ERROR
```
