<div class="heading">
  <div class="name">File Copy</div>
  <div class="command">R←X ⎕FCOPY Y</div>
</div>
# Access Code: 4609

`Y` must be a simple integer scalar or 1 or 2-element vector containing the file tie number and optional passnumber. The file need not be tied exclusively.

`X` is a character vector containing the name of a new file to be copied to.

`⎕FCOPY` creates a copy of the tied file specified by `Y`, named `X`.

The new file `X` will have the same  component level information, including the user number and update time as the original. The operating system file creation, modification and access times will be set to the time at which the copy occurred.

Unless otherwise specified (see File Properties below) the new file `X` will have the same file properties as the original, except that it will be a large-span file regardless of the span of the original.

The result `R` is the file tie number associated with the new file `X`.

Note that the Access Code is 4609, which is the sum of the Access Codes for `⎕FREAD` (1), `⎕FRDCI` (512) and `⎕FRDAC` (4096).

Note also that although the file need not be tied exclusively, the `⎕FCOPY` function will not yield the file to other APL processes while it is running, and it may take some considerable time to run in the case of a large component file.

# Example
```apl
      told←'oldfile32'⎕FTIE 0
      'S' ⎕FPROPS told
32
      tnew←'newfile64' ⎕FCOPY told
 
      'S' ⎕FPROPS tnew
64
```

If `X` specifies the name of an existing file, the operation fails with a `FILE NAME ERROR`.

Note: This operation is atomic. If an error occurs during the copy operation (such as disk full) or if a strong interrupt is issued, the copy will be aborted and the new file `X` will not be created.

# File Properties

`⎕FCOPY` allows you to specify properties for the new file via the variant operator `⍠` used with the following options:

- `'J'` - journaling level; a numeric value.
- `'C'` - checksum level; 0 or 1.
- `'Z'` - compression; 0 or 1.
- `'U'` - Unicode; 0 or 1
- `'S'` - File Size (span); 64

The Principal Option is  as follows:

- 0 - sets `('J' 0) ('C' 0)`
- 1 - sets `('J' 1) ('C' 1)`
- 2 - sets `('J' 2) ('C' 1)`
- 3 - sets `('J' 3) ('C' 1)`

# Examples
```apl
      newfid←'newfile' (⎕FCOPY ⍠3) 1

      'SEUJCZ' ⎕FPROPS newfid
64 0 1 3 1 0

```

Alternatively:
```apl
      JFCOPY←⎕FCOPY ⍠ 3
```

will name a variant of `⎕FCREATE` which will create component file with level 3 journaling, and checksum enabled. Then:
```apl
      newfid←'newfile' JFCOPY 1

```

Note: Setting `('U' 0)` (no Unicode support) is discouraged as it may cause the copy to fail with a `TRANSLATION ERROR`. Similarly using a Classic interpreter to `⎕FCOPY` files may result in `TRANSLATION ERROR`s.
