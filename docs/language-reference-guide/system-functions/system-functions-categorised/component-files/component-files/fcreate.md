<div class="heading">
  <div class="name">File Create</div>
  <div class="command">{R}←X ⎕FCREATE Y</div>
</div>

`Y` must be a simple integer scalar or a 1 or 2 element vector. The first element is the *file tie number*. The second element, if specified, must be 64This element sets the *span* of the file which in earlier Versions of Dyalog APL could be 32 or 64. Small-span (32-bit) component files may no longer be created and this element is retained only for backwards compatibility of code..

The *file tie number* must not be the tie number associated with another tied file.

`X` must be either:

1. a simple character scalar or vector which specifies the name of the file to be created. 
2. a vector of length 1 or 2 whose items are:- a simple character scalar or vector as above.
- an integer scalar specifying the file size limit in bytes.

The newly created file is tied for exclusive use.

The shy result of `⎕FCREATE` is the tie number of the new file.

# Automatic Tie Number Allocation

A tie number of 0 as argument to a create or tie operation, allocates, and returns as an explicit result, the first (closest to zero) available tie number. This allows you to simplify code. For example:

from:
```apl

      tie←1+⌈/0,⎕FNUM     ⍝ With next available number,
      file ⎕FCREATE tie   ⍝ ... create file.

```

to:
```apl

      tie←file ⎕FCREATE 0 ⍝ Create with first available..
```

# Examples
```apl

      '..\BUDGET\SALES'    ⎕FCREATE 2    ⍝ Windows
      '../budget/SALES.85' ⎕FCREATE 2    ⍝ UNIX

      'COSTS' 200000 ⎕FCREATE 4         ⍝ max size 200000

```

# File Properties

`⎕FCREATE` allows you to specify properties for the newly created file via the variant operator `⍠` used with the following options:

- `'J'` - journaling level; a numeric value
- `'C'` - checksum level; 0 or 1
- `'Z'` - compression; 0 or 1
- `'U'` - Unicode; 0 or 1
- `'S'` - File Size (span); 64

The Principal Option is  as follows:

- 0 - sets `('J' 0) ('C' 0)`
- 1 - sets `('J' 1) ('C' 1)`
- 2 - sets `('J' 2) ('C' 1)`
- 3 - sets `('J' 3) ('C' 1)`

See also: [File Properties  on page 1](/fprops.md#FileProperties).

# Examples
```apl
      'newfile' (⎕FCREATE⍠3) 0
1
      'SEUJCZ' ⎕FPROPS 1
64 0 1 3 1 0

```

Alternatively:
```apl
      JFCREATE←⎕FCREATE ⍠ 3
```

will name a variant of `⎕FCREATE` which will create component file with level 3 journaling, and checksum enabled. Then:
```apl
      'newfile'JFCREATE 0
1
```
