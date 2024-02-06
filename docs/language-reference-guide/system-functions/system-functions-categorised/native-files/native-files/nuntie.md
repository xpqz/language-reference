<div class="heading">
  <div class="name">Native File Untie</div>
  <div class="command">{R}←⎕NUNTIE Y</div>
</div>

This closes one or more native files.  `Y` is a scalar or vector of negative integer tie numbers.  The files associated with elements of `Y` are closed.  Native file untie with a zero length argument (`⎕NUNTIE ⍬`) flushes all file buffers to disk - see ["File Untie: " on page 1](/funtie.md#FileUntie) for more explanation.

The shy result of `⎕NUNTIE` is a vector of tie numbers of the files actually untied.
