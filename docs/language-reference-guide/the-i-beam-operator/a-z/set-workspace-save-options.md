<div class="heading">
  <div class="name">Set Workspace Save Options</div>
  <div class="command">R←2400⌶Y</div>
</div>

This function sets a flag in the workspace that determines what happens when it is saved. The flag itself is part of the workspace and is saved with it.

If the flag is set, all Trace, Stop and Monitor settings will be cleared whenever the workspace is saved, whether by `)SAVE`, `⎕SAVE` or by **File/Save** from the Session menubar.

`Y` must be 1 (set the flag) or 0 (clear the flag).

The result `R` is the previous value of the flag.

This function may be extended in the future and a left-argument may be added.

# Example
```apl

      (2400⌶)1
0
      )SAVE
0 Trace bits cleared.
3 Stop bits cleared.
0 Monitor bits cleared.
temp saved Sat Apr 05 17:01:30 2014

```
