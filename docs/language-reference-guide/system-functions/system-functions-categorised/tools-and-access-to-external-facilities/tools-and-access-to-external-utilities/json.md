<div class="heading">
  <div class="name">JSON Convert</div>
  <div class="command">R←{X}⎕JSON Y</div>
</div>

This function imports and exports data in JavaScript Object Notation (JSON) Data Interchange FormatIETF RFC 7159. The JavaScript Object Notation (JSON) Data Interchange Format is a widely supported, text based data interchange format for the portable representation of structured data; any application which conforms to the standard may exchange data with any other..

JSON supports a limited number of data types and there is not a direct correspondence between JSON and APL data structures. In particular:

- JSON does not support arrays with rank >1.
- The JSON standard includes Boolean values true and false which are distinct from numeric values 1 and 0, and have no direct APL equivalent.
- The JSON5 standard includes numeric constants Infinity, -Infinity, NaN and -NaN which have no direct APL equivalent.
- JSON object members are named and these names might not be valid names in APL.

These differences are catered for in various ways as discussed below.

If specified, `X` must be a numeric scalar with the value `0` (import JSON) or  `1` (export JSON). If `X` is not specified and `Y` is a character array, `X` is assumed to be `0` (import); otherwise it is assumed to be 1 (export).

Although this system function was designed with an optional left argument, it is strongly recommended that the argument should always be used.

Other options for `⎕JSON` are Format, Compact, Null, HighRank, Charset and Dialect which are specified using the Variant operator `⍠`. See [Variant on page 1](/primitive-operators/variant.md#Variant). The  Principal Option is Format.

The Dialect Variant option is either `'JSON'` (the default) or `'JSON5'`. The latter enables [JSON5](https//json5org/#) extensions on import and export JSON5 ("JSON5 Data Interchange Format") is an extension of JSON that extends the subset of JavaScript syntax to include optional trailing commas, unquoted object keys, single quoted and multiline strings, additional number formats, and comments..

See also: [JSON Name Mangling on page 1](/json-name-manglling.md#JSON_Name_Mangling).

# JSON Import (X is 0)

`Y` is a character vector or matrix in JSON format. There is an implied newline character between each row of a matrix.

The content of the result `R` depends upon the Format variant which may be `'D'` (the default) or `'M'`.

If Format is `'D'` (which stands for "data") the JSON described by `Y` is converted to APL object(s) and `R` is an array or a namespace containing arrays and sub-namespaces.

- JSON objects are created as APL namespaces.
- JSON null is converted to  the value specified by the Null variant, which may be either `⊂'null'` (the default) or `⎕NULL`.
- JSON true and false and the JSON5 numeric constants Infinity, -Infinity, NaN and -NaN are converted to enclosed character vectors  `⊂'true'`, `⊂'false'` and so forth.
- If the JSON source contains object names which are not valid APL names they are converted to APL objects with mangled names. See [JSON Name Mangling on page 1](/json-name-manglling.md#JSON_Name_Mangling). `7162⌶` can be used to obtain the original name. See [JSON Translate Name on page 1](/i-beam-functions/json-translate-name.md#JSON_Translate_Name).

If Format is `'M'` (which stands for "matrix") the result `R` is a matrix whose columns contain the following:

| `[;1]` | depth |
| --- | --- |
| `[;2]` | name (for JSON object members) |
| `[;3]` | value |
| `[;4]` | JSON type (integer: see below) |

- The representation of null, true and false are the same as for `Format 'D'`.
- Object names are reported as specified in the JSON text; they are not mangled as they are for `Format 'D'`.

JSON data types are as follows:

| Type | Description |
| --- | --- |
| 1 | Object |
| 2 | Array |
| 3 | Numeric |
| 4 | String |
| 5 | Null |
| 6 | No APL equivalent (represented by character string) |
| 7 | JavaScript Object (export only) |

# Duplicate Names

The JSON standard says that members of a JSON object should have unique names and that different implementations behave differently when there are duplicates. Dyalog handles duplicate names as follows:

- No error is generated.
- For `Format 'D'`, the last member encountered is used and  all previous members with the same name are discarded.
- For `Format 'M'` all duplicate members are recorded in the result matrix.

# Examples
```apl
      ⍴JSON
18 19
      JSON
{                  
  "a": {           
    "b": [         
      "string 1",  
      "string 2"   
    ],             
    "c": true,     
    "d": {         
      "e": false,  
      "f⍺": [       
        "string 3",
        123,       
        1000.2,    
        null       
      ]            
    }              
  }                
}                  

```

# Import as Data (Format 'D')

```apl
      j←0 ⎕JSON JSON
      j
#.[JSON object]
      j.⎕NL 9
a
      j.a.⎕NL 2
b
c
      j.a.b
┌────────┬────────┐
│string 1│string 2│
└────────┴────────┘
      j.a.c
┌────┐
│true│
└────┘
      j.a.⎕NL 9
d
      j.a.d.⎕NL 2 ⍝ Note that f⍺ is an invalid APL name
e       
⍙f⍙9082⍙
      j.a.d.e
┌─────┐
│false│
└─────┘
      j.a.d.⍙f⍙9082⍙
┌────────┬───┬──────┬──────┐
│string 3│123│1000.2│┌────┐│
│        │   │      ││null││
│        │   │      │└────┘│
└────────┴───┴──────┴──────┘

```

# Performance Warning

Extracting part of a namespace created by `⎕JSON)` can lead to poor application performance. For example, if you are only interested in an array of records contained as child namespaces that are nested within data that you receive via `⎕JSON`, you might write something like:
```apl
     data←(0 ⎕JSON ⊃⎕NGET filename).records
```

This expression actually creates a temporary namespace `(0 ⎕JSON ⊃⎕NGET filename)` (lets call it `temp` for now), extracts the sub-namespace `records`, and then discards its parent namespace `temp`. The result `data` however contains pointers to `temp`, so although it is not visible (it is unnamed), it is retained internally in the workspace. This  can lead to poor performance due to  the behaviour of the memory manager in this situation. This issue will be resolved in the next release of Dyalog. In the meantime, the situation can  be avoided by assigning a name to the  top-level namespace. Instead of the expression above, you could write:

```apl
      dataset←0 ⎕JSON ⊃⎕NGET filename
      data←dataset.records
```

Giving a name to the top-level namespace effectively avoids the performance issue.

# Import as Matrix (Format 'M')

```apl
      (⎕JSON⍠'M')JSON
┌─┬──┬────────┬─┐
│0│  │        │1│
├─┼──┼────────┼─┤
│1│a │        │1│
├─┼──┼────────┼─┤
│2│b │        │2│
├─┼──┼────────┼─┤
│3│  │string 1│4│
├─┼──┼────────┼─┤
│3│  │string 2│4│
├─┼──┼────────┼─┤
│2│c │┌────┐  │6│
│ │  ││true│  │ │
│ │  │└────┘  │ │
├─┼──┼────────┼─┤
│2│d │        │1│
├─┼──┼────────┼─┤
│3│e │┌─────┐ │6│
│ │  ││false│ │ │
│ │  │└─────┘ │ │
├─┼──┼────────┼─┤
│3│f⍺│        │2│
├─┼──┼────────┼─┤
│4│  │string 3│4│
├─┼──┼────────┼─┤
│4│  │123     │3│
├─┼──┼────────┼─┤
│4│  │1000.2  │3│
├─┼──┼────────┼─┤
│4│  │┌────┐  │5│
│ │  ││null│  │ │
│ │  │└────┘  │ │
└─┴──┴────────┴─┘

```

# JSON Export (X is 1)

`Y` is the data to be exported as JSON and may be an array, a namespace or a matrix representation of JSON such as would have been produced by JSON Import with `Format 'M'`. `Y` is interpreted according to the Format variant which may be `'D'` (the default) or `'M'`.

`⎕JSON` will signal `DOMAIN ERROR` if `Y` is incompatible with the specified (or implied) value of Format.

If Format is `M`, the data values in `Y[;3]` must correspond precisely with the JSON types specified in `Y[;4]`as specified in the following table.

| `Y[;4]` (Type) | `Y[;3]` (Value) |
| --- | --- |
| 1 | Empty array |
| 2 | Empty array |
| 3 | Numeric scalar |
| 4 | Character vector |
| 5 | Null |
| 6 | Enclosed character vector |
| 7 | Enclose character vector |

`R` is a character vector whose content depends upon the value of the Compact variant.

| Compact | Description |
| --- | --- |
| `0` | The JSON text is padded with spaces and new lines for readability. |
| 1 | The JSON text is compacted into its minimal form.. |

The Charset variant option may be used to restrict the output to ASCII characters.

| Charset | Description |
| --- | --- |
| 'Unicode' | All Unicode characters in `Y` are passed unchanged in the result `R` . |
| `'ASCII'` | Non-ASCII characters are converted to an encoded string of the form "\uNNNN" where "NNNN" is the upper-case hexadecimal value of the character in the Unicode system. For example, é (e-acute) is converted to "\u00E9". Furthermore, if the Dialect is JSON5, values less than hex 100 are converted to the form \xNN. |

The HighRank variant option may be used to instruct `⎕JSON` to pre-process higher rank arrays into a form that can be represented by JSON. Note that if necessary, the transformation is applied recursively throughout the high-rank array(s) specified by `Y`.

| HighRank | Description |
| --- | --- |
| `'Split'` | High rank data is split into nested vectors. |
| 'Error' | Higher rank data is rejected ( `DOMAIN ERROR` ) |

The name of any namespace member that begins with `⍙` and otherwise conforms to the conversion format used for JSON object names will be demangled.

# Example
```apl
      j             ⍝ See above
#.[JSON object]
      ⍴JS←1 ⎕JSON j
94
      JS
{"a":{"b":["string 1","string 2"],"c":true,"d":{"e":false,"f⍺":["string 3",123,1000.2,null]}}}

      1(⎕JSON⍠'Compact' 0) j
{
  "a": {
    "b": [
      "string 1",
      "string 2"
    ],
    "c": true,
    "d": {
      "e": false,
      "f⍺": [
        "string 3",
        123,
        1000.2,
        null
      ]
    }
  }
}
```

If there are any mis-matches between the values in `Y[;3]` and the types in `Y[;4]`, `⎕JSON` will signal `DOMAIN ERROR` and report the first row where there is a mis-match (`⎕IO` sensitive) as illustrated in the following example.

# Example
```apl
      M←(⎕JSON⍠'Format' 'M')'{"values": [ 75, 300 ]}'
      M
┌─┬──────┬───┬─┐
│0│      │   │1│
├─┼──────┼───┼─┤
│1│values│   │2│
├─┼──────┼───┼─┤
│2│      │75 │3│
├─┼──────┼───┼─┤
│2│      │300│3│
└─┴──────┴───┴─┘

      M[3;3]←⊂'75' ⍝ character not numeric

      M            ⍝ but looks the same as before
┌─┬──────┬───┬─┐
│0│      │   │1│
├─┼──────┼───┼─┤
│1│values│   │2│
├─┼──────┼───┼─┤
│2│      │75 │3│
├─┼──────┼───┼─┤
│2│      │300│3│
└─┴──────┴───┴─┘
      1 (⎕JSON⍠ 'Format' 'M')M
DOMAIN ERROR: Value does not match the specified type in row 3
      1(⎕JSON⍠'Format' 'M')M
     ∧

```

# Charset Example
```apl
      ns←⎕NS ''
      ns.dé←'DÉ'
      ns.dé
DÉ
      (⎕JSON⍠'Dialect' 'JSON5') ns
{dé:"DÉ"}

```

# High Rank Example
```apl
      d
┌─────┬─────────────────────────┐
│1 2  │ABC                      │
│A B  │DEF                      │
├─────┼─────────────────────────┤
│1 2 3│1            0.5         │
│4 5 6│0.3333333333 0.25        │
│     │                         │
│     │0.2          0.1666666667│
│     │0.1428571429 0.125       │
└─────┴─────────────────────────┘
      1 ⎕JSON d
DOMAIN ERROR: JSON export: the right argument cannot be converted (⎕IO=1)
      1 ⎕JSON d
        ∧
      1 (⎕JSON⍠'HighRank' 'Split') d
[[[[1,2],"AB"],["ABC","DEF"]],[[[1,2,3],[4,5,6]],...

```

# Raw Text

An enclosed character vector is inserted into the result of  JSON export as raw text. This feature may be used to export special JSON values such as null, true and false. Without the extra enclosure, the character vectors are exported as strings:

# Example
```apl
      ⎕JSON 'null' 'true' 'false'
["null","true","false"]
      ⎕JSON ⊂¨'null' 'true' 'false'
[null,true,false]
```

The same mechanism may be used to inject any raw text, although unless this is valid JSON it cannot then be re-imported.

The following example illustrates how JavaScript objects may be exported. In the example, the object is a JavaScript function which is specified by the contents of an enclosed character vector.

# Example
```apl

     'Slider' ⎕NS ''
      Slider.range←⊂'true'         ⍝ Note the ⊂
      Slider.min←0
      Slider.max←500
      Slider.values←75 300
     
      fn1←' function( event, ui ) {'
      fn2←'$( "#amount" ).val( "$" + ui.values[ 0 ] +'
      fn2,←' " - $" + ui.values[ 1 ] );}'
      
      Slider.slide←,/fn1 fn2 ⍝ Enclosed character vec
```
```apl
      ⍴JS←1 ⎕JSON Slider
159
      JS
{"max":500,"min":0,"range":true,"slide": function( event, ui ) {$( \"#amount\" ).val( \"$\" + ui.values[ 0 ] + \" - $\" + ui.values[ 1 ] );},"values":[75,300]}

```

# Wrappers

A wrapper is an enclosed vector of the form:
```apl
     ⊂(code special)
```

The nature of the `special` data structure is identified within the wrapper by a leading numeric code. Code 1 is used to identify JSON values such as `null`, `true` and `false`. Codes 2, 3 and 4 are used to identify different forms of datasets.

This wrapper mechanism has been chosen to identify special treatment because a scalar enclosure cannot be represented in JSON/JavaScript.

A wrapper may be specified directly in the right argument to `⎕JSON` and/or as part of the array structure specified by the right argument, as a sub-array or in a namespace. This allows a special array to be processed appropriately as part of a general data structure that is to be rendered in JSON notation.

# Wrappers for special JSON values

Wrappers may be used to export JSON special values such as null, true and false using code 1. This mechanism is supplementary to the use of enclosed character vectors. See [Raw Text on page 1](/#RawText).

# Example
```apl
      ⎕JSON⊂¨(1 'null')(1 'true')(1 'false')
[null,true,false]
```
