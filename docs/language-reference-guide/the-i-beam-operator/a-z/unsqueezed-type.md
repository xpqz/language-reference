<div class="heading">
  <div class="name">Unsqueezed Type</div>
  <div class="command">R←181⌶Y</div>
</div>

`Y` is any array.

The result `R` is an integer scalar containing an integer value which indicates the type of the array.

`181⌶` is functionally identical to monadic `⎕DR`, except that no attempt is made to squeeze the data into smaller data types. `⎕DR` always attempts to squeeze the data; `181⌶` does not, but if a workspace compaction occurs during execution of `181⌶`, the data may still be squeezed before the type is identified.

# Example
```apl

      ⎕dr 1↑1 1000
11
      (181⌶) 1↑1 1000
163
```
