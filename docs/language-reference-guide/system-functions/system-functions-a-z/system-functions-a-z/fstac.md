<div class="heading">
  <div class="name">File Set Access</div>
  <div class="command">{R}←X ⎕FSTAC Y</div>
</div>
# Access code 8192

`Y` must be a simple integer scalar or 1 or 2 element vector containing the file tie number followed by an optional passnumber. If the passnumber is omitted it is assumed to be zero.

`X` must be a valid access matrix, i.e. a 3-column integer matrix with any number of rows.  The function sets access control for a set of specific users (1st column) and file operations (2nd column) with specified passnumbers ( 3rd column). Note that a 0 in the 1st column specifies all users, a `¯1` in the 2nd column specifies all file operations, and a `0` in the 3rd column specifies that no passnumber is required. For further details, see [File Access Control on page 1](/apl-component-files/component-files.md#File_Access_Control)Component Files.

The shy result of `⎕FSTAC` is the tie number of the file.

# Examples
```apl

      'SALES' ⎕FCREATE 1
      (3 3⍴28 2105 16385 0 2073 16385 31 ¯1 0) ⎕FSTAC 1
      ((⎕FRDAC 1)⍪21 2105 16385) ⎕FSTAC 1

       (1 3⍴0 ¯1 0)⎕FSTAC 2 ⍝ Let everyone do anything

```
