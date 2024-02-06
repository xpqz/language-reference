<div class="heading">
  <div class="name">Workspace Identification</div>
  <div class="command">)WSID {ws}</div>
</div>

This command displays or sets the name of the active workspace.

If a workspace name is not specified, `)WSID` reports the name of the current active workspace.  The name reported is the full path name, including directory references.

If a workspace name is given, the current active workspace is renamed accordingly.  The previous name of the active workspace (excluding directory references) is reported.

# Examples
```apl
      )LOAD WS/TEMP
WS/TEMP saved Thu Sep 17 10:32:19 1998
 
      )WSID
is WS/TEMP
 
      )WSID WS/KEEP
was WS/TEMP
 
      )WSID
WS/KEEP
```
