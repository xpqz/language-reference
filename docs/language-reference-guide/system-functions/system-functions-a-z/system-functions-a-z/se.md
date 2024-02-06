<div class="heading">
  <div class="name">Session Namespace</div>
  <div class="command">⎕SE</div>
</div>

`⎕SE` is a system namespace.  Its GUI components (MenuBar, ToolBar, and so forth) define the appearance and behaviour of the APL Session window and may be customised to suit individual requirements.

`⎕SE` is maintained separately from the active workspace and is not affected by `)LOAD` or `)CLEAR`.  It is therefore useful for containing utility functions.  The contents of `⎕SE` may be saved in and loaded from a .DSE file.

See [The Session Object on page 1](//userguide/the-apl-environment/session-object.md#Session Object) : The Session Object for further details.
