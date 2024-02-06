<div class="heading">
  <div class="name">Native File Exists</div>
  <div class="command">R←⎕NEXISTS Y</div>
</div>

This function reports whether or not file and directories exist.

`Y` is a character vector or scalar containing a single file/directory name, or a vector of character vectors containing zero or more file/directory names.

If `Y` specifies a single name, the result `R` is a scalar 1 if a file or directory exists or 0 if not. If `Y` is a vector of character vectors, `R` is a vector of 1s and 0s with the same length as `Y`.

# Variant Options

`⎕NEXISTS` may be applied using the  Variant operator with the Wildcard option.

If the Wildcard option is 1, `R` indicates whether or not one or more matches to the corresponding pattern in `Y` exist.

# Example
```apl

      ⎕←⎕MKDIR'/Users/Pete/Documents/temp/t1/t2'
1
      ⎕NEXISTS'/Users/Pete/Documents/temp/t1/t2'
1
      ⎕NEXISTS'/Users/Pete/Documents/temp/t1/t2/pd'
0

      ⊢⎕MKDIR'temp1' 'temp2'
1 1
      ⎕NEXISTS 'temp1' 'temp2' 'temp3'
1 1 0
      (⎕NEXISTS⍠1) 't*'
1

```

# Note

If `Y` is a symbolic link, `⎕NEXISTS` will return 1 whether or not the target of the symbolic link exists.
