<div class="heading">
  <div class="name">Expunge Object</div>
  <div class="command">{R}←⎕EX Y</div>
</div>

`Y` must be a simple character scalar, vector or matrix, or a vector of character vectors containing a list of names. `R` is a simple Boolean vector with one element per name in `Y`.

Each name in `Y` is disassociated from its value if the active referent for the name is a defined function, operator, variable or namespace.

The value of an element of `R` is 1 if the corresponding name in `Y` is now available for use.  This does not necessarily mean that the existing value was erased for that name.  A value of  0 is returned for an ill-formed name or for a distinguished name in `Y`.  The result is suppressed if not used or assigned.

# Examples
```apl
      ⎕EX'VAR'
      +⎕EX'FOO' '⎕IO' 'X' '123'
1 0 1 0
```

If a named object is being executed the existing value will continue to be used until its execution is completed.  However, the name becomes available immediately for other use.

# Examples
```apl
      )SI
#.FOO[1]*
 
      ⎕VR'FOO'
     ∇ R←FOO
[1]    R←10
     ∇
      +⎕EX'FOO'
1
      )SI
#.FOO[1]*
 
     ∇FOO[⎕]
defn error
 
      FOO←1 2 3
      →⎕LC
10
      FOO
1 2 3
```

If a named object is an external variable, the external array is disassociated from the name:
```apl
      ⎕XT'F'
FILES/COSTS
      ⎕EX'F' ⋄ ⎕XT'F'
```

If the named object is a GUI object, the object and all its children are deleted and removed from the screen. The expression `⎕EX'.'` deletes all GUI objects owned by the current thread in the Root namespace but not those in sub-namespaces. In addition, if this expression is executed by thread 0, it resets all the properties of  `'.'` to their default values. Furthermore, any unprocessed events in the event queue are discarded.

If the named object is a shared variable, the variable is retracted.

If the named object is the last remaining external function of an auxiliary process, the AP is terminated.

If the named object is the last reference into a dynamic link library, the DLL is freed.
