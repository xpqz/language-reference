<div class="heading">
  <div class="name">Native File Rename</div>
  <div class="command">{R}←X ⎕NRENAME Y</div>
</div>

`⎕NRENAME` is used to rename a native file.

`Y` is a negative integer tie number associated with a tied native file.  `X` is a simple character vector or scalar containing a valid (and unused) file name.

The shy result of `⎕NRENAME` is the tie number of the renamed file.
