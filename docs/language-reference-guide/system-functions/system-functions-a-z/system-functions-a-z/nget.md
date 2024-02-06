<div class="heading">
  <div class="name">Read Text File</div>
  <div class="command">R←{X} ⎕NGET Y</div>
</div>

This function reads the contents of the specified text file. See also [Write Text File on page 1](/nput.md#WriteTextFile).

`Y` is either a character vector/scalar containing the name of the file to be read, or a 2-item vector whose first item is the file name and whose second is an integer scalar specifying `flags` for the operation.

If `flags` is 0 (the default value if omitted) the content in the result `R` is a character vector. If `flags` is 1 the result is a nested array of character vectors corresponding to the lines in the file.

The optional left-argument `X` is either

- a character vector that specifies the file-encoding as shown in the table below.
- 

File Encodings

| Encoding | Description |
| --- | --- |
| `UTF-8` | The data is encoded as UTF-8 format. |
| `UTF-16LE` | The data is encoded as UTF-16 little-endian format. |
| `UTF-16BE` | The data is encoded as UTF-16 big-endian format. |
| `UTF-16` | The data is encoded as UTF-16 with the endianness of the host system (currently BE on AIX platforms, LE on all others). |
| `UTF-32LE` | The data is encoded as UTF-32 little-endian format. |
| `UTF-32BE` | The data is encoded as UTF-32 big-endian format. |
| `UTF-32` | The data is encoded as UTF-32 with the endianness of the host system (currently BE on AIX platforms, LE on all others). |
| `ASCII` | The data is encoded as 7-bit ASCII format. |
| `Windows-1252` | The data is encoded as 8-bit Windows-1252 format. |
| `ANSI` | ANSI is a synonym of Windows-1252. |

The above UTF formats may be qualified with -BOM or -NOBOM (e.g. UTF-8-BOM). See [Write Text File on page 1](/nput.md#WriteTextFile).

Whether or not `X` is specified, if the start of the file contains a recognised   Byte Order Mark (BOM), the file is decoded according to the BOM. Otherwise, if `X` is specified the file is decoded according to the value of `X`. Otherwise, the file is examined to try to decide its encoding and is decoded accordingly.

The result `R` is a 3-element vector comprising `(content) (encoding) (newline)`  where:

| `content` | A simple character vector, or a vector of character vectors, according to the value of `flags` . |
| --- | --- |
| `encoding` | The encoding that was actually used to read the file. If this is a UTF format, it will always include the appropriate endianness (except for UTF-8 to which endianness doesn't apply) and a -BOM or -NOBOM suffix to indicate whether or not a BOM is actually present in the file. For example, UTF-16LE-BOM. If `X` specified a user-defined encoding as a 256-element numeric vector, `encoding` will be that same vector. |
| `newline` | Determined by the first occurrence in the file of one of the newline characters identified in the line separator table, or `⍬` if no such line separator is found. |

If `content` is simple then all its line separators (listed in the table below) are replaced by (normalised to) `⎕UCS 10`, which in the Classic Edition must be in `⎕AVU` (else `TRANSLATION ERROR`).

If `content` is nested, it is formed by splitting the contents of the file on the occurrence of any of the line separators  shown in the table below. These line separators are  removed.

The 3rd element of the result `newline` is a numeric vector from the **Value** column of the table below corresponding to the first occurrence of any of the newline characters in the file. If none of these characters are present, the value is `⍬`.

Line separators:

| Value | Code | Description |
| --- | --- | --- |
| newline characters |
| 13 | `CR` | Carriage Return (U+000D) |
| 10 | `LF` | Line Feed (U+000A) |
| 13 10 | `CRLF` | Carriage Return followed by Line Feed |
| 133 | `NEL` | New Line (U+0085) |
| other line separator characters |
| 11 | `VT` | Vertical Tab (U+000B) |
| 12 | `FF` | Form Feed (U+000C) |
| 8232 | `LS` | Line Separator (U+2028) |
| 8233 | `PS` | Paragraph Separator (U+2029) |
