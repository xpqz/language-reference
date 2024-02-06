<div class="heading">
  <div class="name">Clear Workspace</div>
  <div class="command">)CLEAR</div>
</div>

This command clears the active workspace and gives the report "`clear ws"`.  The active workspace is lost.  The name of a clear workspace is `CLEAR WS`.  System variables are initialised with their default values as described in ["System Variables" on page 1](/system-functions/summary-tables/system-variables.md#SystemVariables).

In GUI implementations of Dyalog APL, `)CLEAR` expunges all GUI objects, discards any unprocessed events in the event queue and resets the properties of the `Root` object  `'.'`  to their default values.

Apart from .NET objects, the contents of the session namespace `⎕SE` are not affected. .NET objects in `⎕SE` are disconnected from .NET because `)CLEAR` closes the current .NET AppDomain.
