<div class="heading">
  <div class="name">File Names</div>
  <div class="command">R←⎕FNAMES</div>
</div>

The result is a character matrix containing the names of all tied files, with one file name per row.  The number of columns is that required by the longest file name.

A file name is returned precisely as it was specified when the file was tied, except that the directory delimiter `\` is replaced by `/`.  If no files are tied, the result is a character matrix with 0 rows and 0 columns.  The rows of the result are in the order in which the files were tied.

# Examples
```apl
      '/usr/pete/SALESFILE' ⎕FSTIE 16
 
      '..\budget\COSTFILE' ⎕FSTIE 2
 
      'PROFIT' ⎕FCREATE 5
 
       ⎕FNAMES
/usr/pete/SALESFILE
../budget/COSTFILE
PROFIT
 
      ⍴⎕FNAMES
3 19
      ⎕FNUMS,⎕FNAMES
16 /usr/pete/SALESFILE
 2 ../budget/COSTFILE
 5 PROFIT
```
