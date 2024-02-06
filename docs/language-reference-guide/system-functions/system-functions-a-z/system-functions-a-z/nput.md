<div class="heading">
  <div class="name">Write Text File</div>
  <div class="command">{R}←X ⎕NPUT Y</div>
</div>

This function writes character data to a text file. See also [Read Text File on page 1](/nget.md#ReadTextFile).

`Y` is either a simple character vector or scalar containing the name of the file to be written, or a 2-item vector whose first item is the file name and whose second is an integer scalar specifying `flags` for the operation.

If `flags` is 0 (the default value if omitted) the file will not be overwritten if it already exists and `⎕NPUT` will signal an error. If `flags` is 1 the file will be overwritten. If flags is 2 the file will be appended to; i.e.

| flags | file does not exist | file exists |
| --- | --- | --- |
| `0` | data is written to new file | error signalled, file is unchanged |
| `1` | data is written to new file | file is overwritten |
| `2` | data is written to new file | data is appended to file |

The left-argument `X` is comprised of 1, 2 or 3 items which identify `(content) (encoding) (newline)` respectively.

`content` is either a vector of character vectors, each of which represents a line in the file to be written, or a simple character vector.

If specified, `encoding` is either:

- a character vector from the first column in the table [File Encodings on page 1](/nget.md#Encodings).  If `encoding` specifies a UTF format, it may be qualified with -BOM  (e.g. UTF-8-BOM), which causes a Byte Order Mark (BOM) to be written at the beginning of the file or -NOBOM which does not. If the -BOM or -NOBOM suffix is omitted, UTF-8 defaults to UTF-8-NOBOM, while the other UTF formats default to -BOM.
- 

If  omitted, `encoding` defaults to UTF-8-NOBOM.

Note: If a non-empty file is appended to:

- No BOM will be written, even if encoding specifies it.
- No check is made that the existing file content is text in the same encoding format.

If specified, `newline` is numeric and is either  `⍬` or a scalar or vector  from the  column labelled **Value** in the newline characters section of the table [Line separators: on page 1](/nget.md#Line_Separators). Any other value causes `DOMAIN ERROR`. If `newline` is omitted it defaults to `(13 10)` on Windows and `10` on other platforms.

In all cases, `newline` is appended if required to a simple vector or to each vector in a vector of vectors.

If content contains anything other than a character vector or scalar (or these, nested) then a `DOMAIN ERROR` is signalled.

If both `encoding` and `newline` are omitted `X` specifies only `content` and may be a simple character vector or a vector of character vectors.

The shy result `R` is the number of bytes written to the file.

# Examples:
```apl
      txt←'mene' 'mene' 'tekel' 'upharsin'

      ⎕←(⊂txt) ⎕NPUT 'writing.txt'
25
      ⊢(⊂'adding' '3' 'lines')⎕NPUT'writing.txt' 2
18
```
```apl
      LF←⎕UCS 10
```
```apl

      t←'adding',LF,'3',LF,'lines',LF
      ⊢t ⎕NPUT'writing.txt' 2
18                                         

```

# NEOL Option

The NEOL variant option specifies how embedded line separators are treated.

| `0` | embedded line separator characters are preserved as is,and a `newline` is added to the last line if required. |
| --- | --- |
| 1 | every embedded LF is replaced by `newline` |
| `2` | every embedded line separator character is replaced by `newline` |
| `¯1` | same as 0 except that a `newline` is not added to the last line |

# Embedded line-separator examples
```apl
      LF CR←⎕UCS 10 13
      t←'adding',LF,'3',CR,'lines',CR,LF
                  
      ⊢t ⎕NPUT'writing.txt' 2                             
17
      ⊢t(⎕NPUT⍠'NEOL' 0)'writing.txt' 2                   
16
      ⊢t(⎕NPUT⍠'NEOL' 2)'writing.txt' 2                   
18
```

`t` contains three lines each with different line endings: LF, CR and CRLF.

In the first example (NEOL is by default 1), only the LF is normalised so the written file contains lines ending with CRLF, CR and CRLF.

In the second example, none of the line endings are normalised so the written file contains lines ending with LF, CR and CRLF.

In the third example, all of the line endings are normalised so the written file contains lines ending with CRLF, CRLF and CRLF.

# Note:

If two or more APL processes separately write to a file using `⎕NPUT` the behaviour is undefined. In particular, if multiple APLs use`⎕NPUT` with flags set to 2 (append), it is not guaranteed that each  `⎕NPUT` operation will be atomic and all the text written to the file will be complete and/or contiguous.
