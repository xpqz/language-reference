<div class="heading">
  <div class="name">Event Number</div>
  <div class="command">R←⎕EN</div>
</div>

This simple integer scalar reports the identification number for the most recent event which occurred, caused by an APL action or by an interrupt or by the `⎕SIGNAL` system function.  Its value in a clear workspace is `0`.

# Example
```apl

      ÷0
DOMAIN ERROR: Divide by zero
      ÷0
     ∧
      ⎕EN
11
```
