<div class="heading">
  <div class="name">Index Origin</div>
  <div class="command">⎕IO</div>
</div>

`⎕IO` determines the index of the first element of a non-empty vector.

`⎕IO` may be assigned the value 0 or 1.  The value in a clear workspace is 1. `⎕IO` has Namespace scope.

`⎕IO` is an implicit argument of any function derived from the Axis operator (`[K]`), of the monadic functions Fix (`⎕FX`), Grade Down (`⍒`), Grade Up (`⍋`), Index Generator (`⍳`), Roll (`?`), and of the dyadic functions Deal (`?`), Grade Down (`⍒`), Grade Up (`⍋`), Index (`⌷`), Index Of (`⍳`), Indexed Assignment, Indexing, Pick (`⊃`) and Transpose (`⍉`).

# Examples
```apl
        ⎕IO←1
        ⍳5
1 2 3 4 5
 
        ⎕IO←0
        ⍳5
0 1 2 3 4
 
        +/[0]2 3⍴⍳6
3 5 7
 
        'ABC',[¯.5]'='
ABC
===
```
