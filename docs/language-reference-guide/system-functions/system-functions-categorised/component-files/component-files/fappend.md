<div class="heading">
  <div class="name">File Append Component</div>
  <div class="command">{R}←X ⎕FAPPEND Y</div>
</div>
# Access code 8

`Y` must be a simple integer scalar or a 1 or 2 element vector containing the file tie number followed by an optional passnumber.  If the passnumber is omitted it is assumed to be zero. Subject to a few restrictions, `X` may be any array.

The shy result `R` is the number of the component to which `X` is written, and is 1 greater than the previously highest component number in the file, or 1 if the file is new.

# Examples
```apl
      (1000?1000) ⎕FAPPEND 1
 
      ⎕←(2 3⍴⍳6) 'Geoff' (⎕OR'FOO') ⎕FAPPEND 1
12
 
      ⎕←A B C ⎕FAPPEND¨1
13 14 15

Dump←{
    tie←⍺ ⎕FCREATE 0              ⍝ create file.
    (⎕FUNTIE tie){}⍵ ⎕FAPPEND tie ⍝ append and untie.
}
```
