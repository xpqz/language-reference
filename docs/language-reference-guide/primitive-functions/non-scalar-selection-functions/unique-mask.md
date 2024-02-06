<div class="heading">
  <div class="name">Unique Mask</div>
  <div class="command">R←≠Y</div>
</div>

`Y` may be any array.

`R` is a Boolean vector whose length is the number of major cells
in `Y`. For each major cell of `Y`, the corresponding element of  `R` is 1 if it is the first occurrence of that value, and 0 if it is a duplicate of an earlier major cell.

`⎕CT` and `⎕DCT` are  implicit arguments of Unique.

# Examples
```apl
      ≠22 10 22 22 21 10 5 10
1 1 0 0 1 0 1 0

```
```apl

      ≠ v←'CAT' 'DOG' 'CAT' 'DUCK' 'DOG' 'DUCK'
1 1 0 1 0 0

      ⊢mat←↑v 
CAT 
DOG 
CAT 
DUCK
DOG 
DUCK
      ≠mat
1 1 0 1 0 0

```
