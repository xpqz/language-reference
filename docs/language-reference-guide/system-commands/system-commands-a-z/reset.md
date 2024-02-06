<div class="heading">
  <div class="name">Reset State Indicator</div>
  <div class="command">)RESET {n}</div>
</div>

This command cancels all suspensions recorded in the state indicator and discards any unprocessed events in the event queue.

The optional parameter `n` specifies that only the top `n` suspensions are to be cleared.

`)RESET` also performs an internal re-organisation of the workspace and process memory. See ["Workspace Available: " on page 1](/system-functions/wa.md#WorkspaceAvailable)  for details.

# Example
```apl
      )SI
#.FOO[1]*
⍎
#.FOO[1]*
 
      )RESET
 
      )SI
```
