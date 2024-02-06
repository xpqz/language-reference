<div class="heading">
  <div class="name">Cross References</div>
  <div class="command">R←⎕REFS Y</div>
</div>

`Y` must be a simple character scalar or vector, identifying the name of a function or operator, or the object representation form of a function or operator (see ["Object Representation: " on page 1](/or.md#ObjectRepresentation)).  `R` is a simple character matrix, with one name per row, of identified names in the function or operator in `Y` excluding distinguished names of system constants, variables or functions.

# Example
```apl
      ⎕VR'OPTIONS'
     ∇ OPTIONS;OPTS;INP
[1]   ⍝ REQUESTS AND EXECUTES AN OPTION
[2]    OPTS ←'INPUT' 'REPORT' 'END'
[3]   IN:INP←ASK'OPTION:'
[4]    →EX⍴⍨(⊂INP)∊OPTS
[5]    'INVALID OPTION. SELECT FROM',OPTS ⋄ →IN
[6]   EX:→EX+OPTS⍳⊂INP
[7]    INPUT ⋄ →IN
[8]    REPORT ⋄ →IN
[9]   END:
     ∇
 
    ⎕REFS'OPTIONS'
ASK
END
EX
IN
INP
INPUT
OPTIONS
OPTS
REPORT
```

If `Y` is locked or is an External Function, `R` contains its name only.  For example:
```apl
      ⎕LOCK 'OPTIONS' ⋄ ⎕REFS 'OPTIONS'
OPTIONS
```

If `Y` is the name of a primitive, external or derived function, `R` is an empty matrix with shape 0 0.
