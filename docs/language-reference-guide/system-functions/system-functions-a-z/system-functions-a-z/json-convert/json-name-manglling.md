# JSON Name Mangling

## JSON Name Mangling

When Dyalog converts from JSON to APL data, and a member of a JSON object has a name which is not a valid APL name, it is renamed.

## Example:

In this example, the JSON describes an object containing two numeric items, one named **a** (which is a valid APL name) and the other named **2a** (which is not):
{"a": 1, "2a": 2}

When this JSON is imported as an APL namespace using `⎕JSON`, Dyalog converts the name **2a** to a valid APL name. The *name mangling* algorithm creates a name beginning with `⍙`.
```apl
      (⎕JSON'{"a": 1, "2a": 2}').⎕NL 2
a  
⍙2a
```

When Dyalog exports JSON it performs the reverse *name mangling*, so:
```apl
      1 ⎕JSON ⎕JSON'{"a": 1, "2a": 2}'
{"a":1,"2a":2}

```

Should you need to create and decode these names directly,`7162⌶` provides the same name mangling and un-mangling operations. See [JSON Translate Name on page 1](/i-beam-functions/json-translate-name.md#JSON_Translate_Name).
```apl
      0(7162⌶)'2a'
⍙2a
      1(7162⌶)'⍙2a'
2a

```
