<div class="heading">
  <div class="name">Using (Microsoft .NET Search Path)</div>
  <div class="command">⎕USING</div>
</div>

`⎕USING` specifies a list of Microsoft .NET Namespaces that are to be searched for a reference to a .NET class. `⎕USING` has Namespace scope.

# Examples:
```apl
  ⎕USING←'System'
  ]display ⎕USING
.→---------.
| .→-----. |
| |System| |
| '------' |
'∊---------'

⎕USING,←⊂'System.Windows.Forms,System.Windows.Forms.dll'
⎕USING,←⊂'System.Drawing,System.Drawing.dll'
```

An Assembly may contain top-level classes which are not packaged into .NET Namespaces. In this case, you omit the Namespace name. For example:
```apl
  ⎕USING←,⊂',.\LoanService.dll'
```
