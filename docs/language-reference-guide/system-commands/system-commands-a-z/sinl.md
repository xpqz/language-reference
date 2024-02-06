<div class="heading">
  <div class="name">State Indicator & Name List</div>
  <div class="command">)SINL</div>
</div>

This command displays the contents of the state indicator together with local names. The display is the same as for `)SI` (see above) except that a list of local names is appended to each defined function or operator line.

# Example

```apl
      )SINL
#.PLUS[2]*        B       A       R       DYADIC  END
.
#.MATDIV[4]       R       END     I       J       ⎕TRAP
#.FOO[1]* R
⍎
```
