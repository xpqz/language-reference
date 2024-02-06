<div class="heading">
  <div class="name">List Global Defined Functions</div>
  <div class="command">)FNS {nm}</div>
</div>

This command displays the names of global defined functions in the active workspace or current namespace.  Names are displayed in `⎕AV` collation order.  If a name is included after the command, only those names starting at or after the given name in collation order are displayed.

# Examples
```apl
      )FNS
ASK DISPLAY GET PUT ZILCH
      )FNS G
GET PUT ZILCH
```
