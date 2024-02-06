<div class="heading">
  <div class="name">Discard Thread on Exit</div>
  <div class="command">R←2501⌶Y</div>
</div>

`(2501⌶0)`
 must be called from WITHIN one of these threads and tells the interpreter NOT to park the thread on termination, but to discard the thread completely.
