<div class="heading">
  <div class="name">File Rename</div>
  <div class="command">{R}←X ⎕FRENAME Y</div>
</div>
# Access code 128

`Y` must be a simple 1 or 2 element integer vector containing a file tie number and an optional passnumber.  If the passnumber is omitted it is assumed to be zero.

`X` must be a simple character scalar or vector containing the new name of the file.  This name must be in accordance with the operating system's conventions, and may be specified with a relative or absolute pathname.

The file being renamed must be tied exclusively.

The shy result of `⎕FRENAME` is the tie number of the file.

# Examples
```apl
      'SALES' ⎕FTIE 1
      'PROFIT' ⎕FTIE 2
 
      ⎕FNAMES
SALES
PROFIT
 
      'SALES.85' ⎕FRENAME 1
      '../profits/PROFITS.85' ⎕FRENAME 2
```
```apl
      ⎕FNAMES
SALES.85
../profits/PROFITS.85
 
Rename←{
    fm to←⍵
    ⎕FUNTIE to ⎕FRENAME fm ⎕FTIE 0
}
```
