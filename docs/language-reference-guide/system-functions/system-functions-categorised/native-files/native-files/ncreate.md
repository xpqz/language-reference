<div class="heading">
  <div class="name">Native File Create</div>
  <div class="command">{R}←X ⎕NCREATE Y</div>
</div>

This function creates a new file. Under Windows the file is opened with mode 66 (see [Native File Tie on page 1](/ntie.md#NativeFileTie)). Under non-Windows operating systems the current umask will specify the file permissions. The name of the new file is specified by the left argument `X` which must be a simple character vector or scalar containing a valid pathname for the file.

`Y` is 0 or a negative integer value that specifies an (unused) tie number by which the file may subsequently be referred. If `Y` is 0, the system allocates the first (closest to zero) available tie number which is returned as the result.

The shy result of `⎕NCREATE` is the tie number of the new file.

# Variant Options

`⎕NCREATE` may be applied using the  Variant operator with the options Unique and IfExists. There is no primary option.

# Unique Option (Boolean)

| 0 | the file named by `X` will be created |
| --- | --- |
| `1` | a uniquely named file will be created by extending the base name (see [File Name Parts on page 1](/nparts.md#NParts) ) with random characters. If a unique name cannot be created then an error will be signalled. The actual name of the file can be determined from `⎕NNAMES` or `⎕NINFO` . |

# IfExists Option (character vector)

| Error | `⎕NCREATE` will generate a `FILE NAME ERROR` if the file already exists |
| --- | --- |
| `Replace` | `⎕NCREATE` will replace an existing file with an empty one of the same name. |

# Examples
```apl
      ⊢'myfile' ⎕NCREATE 0
¯1
      ⎕NUNTIE ¯1
      ⊢'myfile' ⎕NCREATE 0
FILE NAME ERROR: myfile: Unable to create file ("The file exists.")
      ⊢'myfile'⎕NCREATE 0
               ∧
```
```apl

      ⊢'myfile' (⎕NCREATE⍠'IfExists' 'Replace') 0
```
```apl
¯1    ⍝ Note that it uses same tie number as before

```
```apl

      ⊢'myfile' (⎕NCREATE⍠('Unique' 1)) 0
¯2
      ⎕NNUMS,⎕NNAMES
¯1 myfile      
¯2 myfile52c36z

```

# Notes:

- Setting IfExists to `Replace` has no effect when Unique is 1, because the file cannot already exist.
- The IfExists option does not affect the operation of *slippery ties*.
