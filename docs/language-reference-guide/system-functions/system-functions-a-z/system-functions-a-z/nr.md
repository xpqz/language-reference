<div class="heading">
  <div class="name">Nested Representation</div>
  <div class="command">R←⎕NR Y</div>
</div>

`Y` must be a simple character scalar or vector which represents the name of a function or a defined operator.

If `Y` is a name of a defined function or defined operator, `R` is a vector of text vectors.  The first element of `R` contains the text of the function or operator header.  Subsequent elements contain lines of the function or operator.  Elements of `R` contain no unnecessary blanks, except for leading indentation of control structures and the blanks which precede comments.

If `Y` is the name of a variable, a locked function or operator, an external function or a namespace, or is undefined, `R` is an empty vector.

# Example
```apl
      ∇R←MEAN X    ⍝ Average
[1]   R←(+/X)÷⍴X
      ∇
 
      +F←⎕NR'MEAN'
  R←MEAN X    ⍝Average   R←(+/X)÷⍴X
 
      ⍴F
2
      ]display F
.→----------------------------------------.
| .→---------------------.  .→----------. |
| | R←MEAN X    ⍝ Average|  | R←(+/X)÷⍴X| |
| '----------------------'  '-----------' |
'∊----------------------------------------'
```

The definition of `⎕NR` has been extended to names assigned to functions by specification (`←`), and to local names of functions used as operands to defined operators.  In these cases, the result of `⎕NR` is identical to that of `⎕CR` except that the representation of defined functions and operators is as described above.

# Example
```apl
      AVG←MEAN∘,
 
      +F←⎕NR'AVG'
   R←MEAN X    ⍝ Average   R←(+/X)÷⍴X  ∘,
 
      ⍴F
3
      ]display F
.→------------------------------------------------.
| .→----------------------------------------.     |
| | .→---------------------.  .→----------. | ∘ , |
| | | R←MEAN X    ⍝ Average|  | R←(+/X)÷⍴X| | - - |
| | '----------------------'  '-----------' |     |
| '∊----------------------------------------'     |
'∊------------------------------------------------'
```
