<div class="heading">
  <div class="name">Lock Definition</div>
  <div class="command">{R}←{X}⎕LOCK Y</div>
</div>

`Y` must be a simple character scalar, or vector which is taken to be the name of a defined function or operator in the active workspace. `⎕LOCK` does not apply to dfns or derived functions.

The active referent to the name in the workspace is locked.  Stop, trace and monitor settings, established by the `⎕STOP`, `⎕TRACE` and `⎕MONITOR` functions, are cancelled.

The optional left argument `X` specifies to what extent the function code is hidden. `X` may be 1, 2 or 3 (the default) with the following meaning:

1. The object may not be displayed and you may not obtain its character form using `⎕CR`, `⎕VR` or `⎕NR`.
2. If an error or exception occurs that would normally cause a suspension of execution within the locked function or operator, the state indicator is cut back to the statement that called it and the suspension is triggered there instead.
3. Both 1 and 2 apply. You can neither display the locked object nor suspend execution within it.

Locks are additive, so that
```apl
      1 ⎕LOCK'FOO' ⋄ 2 ⎕LOCK'FOO'     
```

is equivalent to:
```apl
      3 ⎕LOCK'FOO' 
```

The shy result `R` is the lock state (1,2 or 3) of `Y`.

A `DOMAIN ERROR` is reported if `Y` is ill-formed.

# Examples
```apl
      ⎕FX'r←foo' 'r←10'
      ⎕NR'foo'  
  r←foo r←10
      ⍴⎕NR'foo'
2
      ⎕LOCK'foo'
      ⍴⎕NR'foo'
0

```
