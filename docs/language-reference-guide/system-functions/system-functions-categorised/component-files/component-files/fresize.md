<div class="heading">
  <div class="name">File Resize</div>
  <div class="command">{R}←{X}⎕FRESIZE Y</div>
</div>
# Access code 1024

`Y` must be a simple integer scalar or 1 or 2 element vector containing the file tie number followed by an optional passnumber.  If the passnumber is omitted it is assumed to be zero.

`X` is an integer that specifies the maximum permitted size of the file in bytes. The value 0 means the maximum possible size of file.

An attempt to update a component file that would cause it to exceed its maximum size will fail with a `FILE FULL` error (21). A side effect of `⎕FRESIZE` is to cause the file to be compacted. This process removes any gaps in the file caused by replacing a component with a shorter array. Any interrupt entered at the keyboard during the compaction is ignored. Note that if the left argument is omitted, the file is simply compacted and the maximum file size remains unchanged.

During compaction, the file is restructured by reordering the components and by amalgamating the free areas at the end of the file. The file is then truncated and excess disk space is released back to the operating system. For a large file with many components, this process may take a significant time.

The shy result of `⎕FRESIZE` is the tie number of the file.

# Example
```apl
      'test'⎕FCREATE 1 ⋄ ⎕FSIZE 1
1 1 120 1.844674407E19
      (10 1000⍴1.1)⎕FAPPEND 1 ⋄ ⎕FSIZE 1
1 2 80288 1.844674407E19
 
      100000 ⎕FRESIZE 1 ⍝ Limit size to 100000 bytes
 
      (10 1000⍴1.1)⎕FAPPEND 1
FILE FULL
      (10 1000⍴1.1)⎕FAPPEND 1
     ∧
 
      ⎕FRESIZE 1      ⍝ Force file compaction.
```
