<div class="heading">
  <div class="name">Protected Copy</div>
  <div class="command">)PCOPY {ws {nms}}</div>
</div>

This command brings all or selected global objects from a stored workspace with the given name provided that there is no existing global usage of the name in the active workspace.  A stored workspace is one which has previously been saved with the system command `)SAVE` or the system function `⎕SAVE`.

`)PCOPY` does not copy `⎕SM`.  This restriction may be removed in a later release.

If the workspace name is not valid or does not exist or if access to the workspace is not authorised, the system reports "`ws not found`".  If the workspace name identifies a file that is not a workspace, or is a workspace with an invalid version number (one that is greater than the version of the current APL) the system reports "`bad ws`".

If the workspace name is the name of a valid, readable workspace, the system reports the workspace name, "`saved`", and the date and time that the workspace was last saved.

If the list of names is excluded, all global defined objects (functions and variables) are copied.  If an object is not found in the stored workspace, the system reports "`not found`" followed by the name of the object. If an object cannot be copied into the active workspace because there is an existing referent, the system reports "`not copied`" followed by the name of the object.

For further information, see ["Copy Workspace: " on page 1](/system-functions/cy.md#CopyWorkspace:).

# Examples
```apl
      )PCOPY WS/UTILITY
WS/UTILITY saved Mon Nov  1 13:11:19 1993
not copied COPIED IF
not copied COPIED JOIN
 
      )PCOPY TEMP FOO X
./TEMP saved Mon Nov  1 14:20:47 1993
not found X
```

# Warning

If a workspace full condition occurs during the execution of `)PCOPY` the state of the active workspace is unpredictable.
