<div class="heading">
  <div class="name">Load without Latent Expression</div>
  <div class="command">)XLOAD {ws}</div>
</div>

This command causes the named stored workspace to be loaded.  The current active workspace is lost.

`)XLOAD` is identical in effect to `)LOAD` except that `)XLOAD` does not cause the expression defined by the latent expression `⎕LX` in the saved workspace to be executed.
