<div class="heading">
  <div class="name">Edit Object</div>
  <div class="command">)ED nms</div>
</div>

`)ED` invokes the Dyalog APL editor and opens an Edit window for each of the objects specified in `nms`.

If a name includes the slash character  ("\" or "/") it is taken to be the name of a file. See [Editing Scripts and Text Files on page 1](//userguide/the-apl-environment/editing-scripts-and-text-files.md#Editing_Text)Editing Scripts and Text Files.

If a name is followed by a line number specified in square brackets, the Editor positions the cursor in the corresponding line. There must not be a space between the last character of the name and the "[".

If a name specifies a new symbol it is taken to be a function or operator.  However, if a name is localised in a suspended function or operator but is otherwise undefined, it is assumed to be a vector of character vectors.

The type of a new object may be specified explicitly by preceding its name with an appropriate symbol as follows:

| `∇` | function or operator |
| --- | --- |
| `→` | simple character vector |
| `∊` | vector of character vectors |
| `-` | character matrix |
| `⍟` | Namespace script |
| `○` | Class script |
| `∘` | Interface |

The first object named becomes the top window on the stack.  See the *Dyalog for Microsoft Windows UI Guide* or the *Dyalog for UNIX UI Guide* for details.

# Examples
```apl

      )ED MYFUNCTION

      )ED MYFUNCTION[1000] YOURFUNCTION[3]

      )ED ∇FOO -MAT ∊VECVEC

```

Objects specified in `nms` that cannot be edited are silently ignored. Objects qualified with a namespace path  (e.g.`a.b.c.foo`) are silently ignored if the namespace does not exist.
