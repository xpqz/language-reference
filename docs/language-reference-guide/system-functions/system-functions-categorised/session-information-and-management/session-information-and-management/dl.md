<div class="heading">
  <div class="name">Delay</div>
  <div class="command">{R}←⎕DL Y</div>
</div>

`Y` must be a simple non-negative single numeric value (of any rank).  A pause of approximately `Y` seconds is caused.

The shy result `R` is a scalar numeric value indicating the length of the pause in seconds.

The pause may be interrupted by a weak or strong interrupt.
