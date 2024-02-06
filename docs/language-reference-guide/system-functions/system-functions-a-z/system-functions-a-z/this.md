<div class="heading">
  <div class="name">This Space</div>
  <div class="command">R←⎕THIS</div>
</div>

`⎕THIS` returns a reference to the current namespace, i.e. to the space in which it is referenced.

If `NC9` is a reference to any object whose name-class is `9`, then:
```apl
      NC9≡NC9.⎕THIS
1
```

# Examples
```apl
      ⎕THIS
#
      'X'⎕NS ''
      X.⎕THIS
#.X
     'F'⎕WC'Form'
     'F.B'⎕WC'Button'
      F.B.⎕THIS
#.F.B
 
      Polly←⎕NEW Parrot
      Polly.⎕THIS
#.[Parrot]
```

An Instance may use `⎕THIS` to obtain a reference to its own Class:
```apl
    Polly.(⊃⊃⎕CLASS ⎕THIS)
#.Parrot
```

or a function (such as a Constructor or Destructor) may identify or enumerate all other Instances of the same Class:
```apl
      Polly.(⍴⎕INSTANCES⊃⊃⎕CLASS ⎕THIS)
1
```
