<div class="heading">
  <div class="name">Native File Erase</div>
  <div class="command">{R}←X ⎕NERASE Y</div>
</div>

This function erases (deletes) a tied native file.  `Y` is a negative integer tie number associated with a tied native file.  `X` is a simple character vector or scalar containing the name of the same file and must be identical to the name used when it was opened by `⎕NCREATE` or `⎕NTIE`.

The shy result of `⎕NERASE` is the tie number that the erased file had.

# Example
```apl
      file ⎕nerase file ⎕ntie 0
```
