<div class="heading">
  <div class="name">Diagnostic Message</div>
  <div class="command">R←⎕DM</div>
</div>

This niladic function returns the last reported APL error as a three-element vector, giving error message, line in error and position of caret pointer.

# Example
```apl

      2÷0
DOMAIN ERROR
      2÷0
     ^

      ⎕DM
 DOMAIN ERROR        2÷0       ^
```
