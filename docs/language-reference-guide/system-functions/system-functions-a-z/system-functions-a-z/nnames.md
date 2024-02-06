<div class="heading">
  <div class="name">Native File Names</div>
  <div class="command">R←⎕NNAMES</div>
</div>

This niladic function reports the names of all currently open native files.  `R` is a character matrix.  Each row contains the name of a tied native file padded if necessary with blanks.  The names are identical to those that were given when opening the files with `⎕NCREATE` or `⎕NTIE`. The rows of the result are in the order in which the files were tied.
