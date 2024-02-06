<div class="heading">
  <div class="name">Native File Numbers</div>
  <div class="command">R←⎕NNUMS</div>
</div>

This niladic function reports the tie numbers associated with all currently open native files.  `R` is an integer vector of negative tie numbers. The elements of the result are in the order in which the files were tied.
