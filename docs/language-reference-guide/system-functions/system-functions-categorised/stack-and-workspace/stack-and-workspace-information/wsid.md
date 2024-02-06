<div class="heading">
  <div class="name">Workspace Identification</div>
  <div class="command">⎕WSID</div>
</div>

This is a simple character vector.  It contains the identification name of the active workspace.  If a new name is assigned, that name becomes the identification name of the active workspace, provided that it is a correctly formed name.

See [Workspaces](/introduction/workspaces.md#Workspaces) for workspace naming conventions.

It is useful, though not essential, to associate workspaces with a specific directory in order to distinguish workspaces from other files.

The value of `⎕WSID` in a clear workspace is `'CLEAR WS'`. `⎕WSID` has workspace scope.

# Example
```apl

      ⎕WSID
CLEAR WS

      ⎕WSID←'ws/mywork       (UNIX)

      ⎕WSID←'B:\WS\MYWORK'   (Windows)

```
