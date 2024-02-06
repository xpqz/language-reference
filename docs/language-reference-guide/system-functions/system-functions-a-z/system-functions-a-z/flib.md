<div class="heading">
  <div class="name">Component File Library</div>
  <div class="command">R←⎕FLIB Y</div>
</div>

`Y` must be a simple character scalar or vector which specifies the name of the directory whose APL component files are to be listed.  If `Y` is empty, the current working directory is assumed.

The result `R` is a character matrix containing the names of the component files in the directory with one row per file.  The number of columns is given by the longest file name.  Each file name is prefixed by `Y` followed by a directory delimiter character.  The ordering of the rows is not defined.

If there are no APL component files accessible to the user in the directory in question, the result is an empty character matrix with 0 rows and 0 columns.

# Examples
```apl

      ⎕FLIB ''
SALESFILE
COSTS

      ⎕FLIB '.'
./SALESFILE
./COSTS

      ⎕FLIB '../budget'
../budget/SALES.85
../budget/COSTS.85
```
