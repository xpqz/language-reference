<div class="heading">
  <div class="name">Namespace</div>
  <div class="command">{R}←{X}⎕NS Y</div>
</div>

If specified, `X` must be a simple character scalar or vector identifying the name of a namespace.

`Y` is either a character array which represents a list of names of objects to be copied into the namespace, or a ref to a namespace, or  an array produced by the `⎕OR` of a namespace.

# Case 1

In the first case, `Y` must be a simple character scalar, vector, matrix or a nested vector of character vectors identifying zero or more workspace objects to be copied into the namespace `X`.  The identifiers in `X` and `Y` may be simple names or compound names separated by `'.'` and including the names of the special namespaces `'#'`, `'##'` and `'⎕SE'`.

The namespace `X` is created if it doesn't already exist.  If the name is already in use for an object other than a namespace, APL issues a `DOMAIN ERROR`.

If `X` is omitted, an unnamed namespace is created.

The objects identified in the list `Y` are copied into the namespace `X`.

If `X` is specified, the result `R` is the full name (starting with `#.` or `⎕SE.`) of the namespace `X`. If `X` is omitted, the result `R` is a namespace reference, or *ref*, to an unnamed namespace.

# Examples
```apl
      +'X'⎕NS''               ⍝ Create namespace X.
#.X
      ⊢'X'⎕NS'VEC' 'UTIL.DISP'⍝ Copy VEC and DISP to X.
#.X
      )CS X                   ⍝ Change to namespace X.
#.X
      ⊢'Y'⎕NS'#.MAT' '##.VEC' ⍝ Create #.X.Y &copy in
#.X.Y
      ⊢'#.UTIL'⎕NS'Y.MAT'     ⍝ Copy MAT from Y to UTIL #.UTIL.
#.UTIL
      ⊢'#'⎕NS'Y'              ⍝ Copy namespace Y to root.
#

```
```apl
      ⊢''⎕NS'#.MAT'           ⍝ Copy MAT to current space.
#.X
      ⊢''⎕NS''                ⍝ Display current space.
#.X
      ⊢'Z'⎕NS ⎕OR'Y'          ⍝ Create nspace from ⎕OR.
#.X.Z
```
```apl
      NONAME←⎕NS ''           ⍝ Create unnamed nspace
      NONAME
#.[Namespace]
```
```apl
      DATA←⎕NS¨3⍴⊂''         ⍝ Create 3-element vector of
                             ⍝ distinct unnamed nspaces
      DATA
 #.[Namespace]  #.[Namespace]  #.[Namespace]
```

# Case 2

The second case is where `Y` is a ref to a namespace or the `⎕OR` of a namespace.

If `Y` is a ref to or a `⎕OR` of a *GUI*object, `X` must be a valid parent for the GUI object represented by `Y`, or the operation will fail with a `DOMAIN ERROR`.

Otherwise, the result of the operation depends upon the existence of `X`.

- If `X` does not currently exist (name class is 0), `X` is created as a complete copy (clone) of the original namespace represented by `Y`. If `Y` is a ref to or the `⎕OR` of a GUI object or of a namespace containing GUI objects, the corresponding GUI components of `Y` will be instantiated in `X`.
- If `X` is the name of an existing namespace (name class 9), the contents of `Y`, including any GUI components, are merged into `X`. Any items in `X` with corresponding names in `Y` (names with the same path in both `Y` and `X`) will be replaced by the names in `Y`, unless they have a conflicting name class in which case the existing items in `X` will remain unchanged. However, all GUI spaces in `X` will be stripped of their GUI components prior to the merge operation.
