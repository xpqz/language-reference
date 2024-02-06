<div class="heading">
  <div class="name">Save Continuation</div>
  <div class="command">)CONTINUE</div>
</div>

This command saves the active workspace in the current working directory and ends the Dyalog APL session. The name of the workspace file is CONTINUE in upper-case with the extension defined by the [WSEXT parameter](//userguide/installation-and-configuration/configuration-parameters.md#WSEXT). See Configuration Parameters.

Note that the values of all system variables (including `⎕SM`) and GUI objects are also saved in `CONTINUE`.

When a `CONTINUE` workspace is loaded, the latent expression (if any) is NOT executed.
