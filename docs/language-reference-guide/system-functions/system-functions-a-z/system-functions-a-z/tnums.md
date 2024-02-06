<div class="heading">
  <div class="name">Thread Numbers</div>
  <div class="command">R←⎕TNUMS</div>
</div>

`⎕TNUMS` reports the numbers of all current threads.

`R` is a simple integer vector of the base thread and all its living descendants.

# Example
```apl
      ⎕TNUMS
0 2 4 5 6 3 7 8 9
```
