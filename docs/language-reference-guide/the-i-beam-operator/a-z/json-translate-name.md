<div class="heading">
  <div class="name">JSON Translate Name</div>
  <div class="command">R←X(7162⌶)Y</div>
</div>

Converts between JSON names and APL names.

When `⎕JSON` imports an entity from JSON text whose name would be an invalid APL name, the function converts the invalid name into a valid APL name using a *name mangling* algorithm. When `⎕JSON` exports an APL namespace as JSON text, the process is reversed.

This function performs the same *name mangling* allowing the programmer to identify JSON entities as APL names, and vice-versa.

`Y` is a character vector or scalar.

`X` is a scalar numeric value which must be 1 or 0.

When `X` is 0, `R` is the name in `Y` converted, if necessary, so that it is a valid APL name. It performs the same translation of JSON object names to APL names that is performed when importing JSON.

When `X` is 1, `R` is the name in `Y` which, if mangled, is converted back to the original form.. It performs the same translation of APL names to JSON object names that is performed when exporting JSON.

# Examples:
```apl
      0(7162⌶)'2a'
⍙2a
      1(7162⌶)'⍙2a'
2a
```
```apl
      0(7162⌶)'foo'
foo
      1(7162⌶)'foo'
foo

```

Note that the algorithm can be applied, even when mangling is not required. So:
```apl
      1(7162⌶)'⍙97'
a
```

For further details, see [JSON Name Mangling on page 1](/system-functions/json.md#JSON_Name_Mangling).
