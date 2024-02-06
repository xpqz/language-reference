<div class="heading">
  <div class="name">Transpose (Monadic)</div>
  <div class="command">R←⍉Y</div>
</div>

`Y` may be any array.  `R` is an array of shape `⌽⍴Y`, similar to `Y` with the order of the axes reversed.

# Examples
```apl
      M
1 2 3
4 5 6
 
      ⍉M
1 4
2 5
3 6
```

```apl

      cube    ⍝ 3D array
 1  2  3  4
 5  6  7  8
 9 10 11 12
           
13 14 15 16
17 18 19 20
21 22 23 24

      ⍉ cube
 1 13
 5 17
 9 21
     
 2 14
 6 18
10 22
     
 3 15
 7 19
11 23
     
 4 16
 8 20
12 24

      ⍴ cube
2 3 4
      ⍴ ⍉ cube    ⍝ transpose reverses shape
4 3 2

```
