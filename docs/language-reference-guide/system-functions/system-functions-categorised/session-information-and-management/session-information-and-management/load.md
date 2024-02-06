<div class="heading">
  <div class="name">Load Workspace</div>
  <div class="command">⎕LOAD Y</div>
</div>

`Y` must be a simple character scalar or vector containing the name of a file that contains a saved workspace. . If no file extension is given it is implied. See WSEXT configuration parameter[WSEXT on page 1](//userguide/installation-and-configuration/configuration-parameters/wsext.md#WSEXT).

If `Y` is ill-formed or does not identify a saved workspace or the user account does not have access permission to the workspace, a `DOMAIN ERROR` is reported.

Otherwise, the active workspace is replaced by the workspace identified in `Y`.  The active workspace is lost.  If the loaded workspace was saved by the `)SAVE` system command, the latent expression (`⎕LX`) is immediately executed, unless APL was invoked with the -x option.  If the loaded workspace was saved by the `⎕SAVE` system function, execution resumes from the point of exit from the `⎕SAVE` function, with the result of the `⎕SAVE` function being 0, running in the same namespace in which the `⎕SAVE` was executed.

The workspace identification and time-stamp when saved is not displayed.

If the workspace contains any GUI objects whose `Visible` property is 1, these objects will be displayed.  If the workspace contains a non-empty `⎕SM` but does not contain an SM GUI object, the form defined by `⎕SM` will be displayed in a window on the screen.

The system switches to the namespace that was the current namespace when the workspace was saved.
