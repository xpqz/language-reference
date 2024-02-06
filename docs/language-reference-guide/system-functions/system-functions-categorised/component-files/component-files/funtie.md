<div class="heading">
  <div class="name">File Untie</div>
  <div class="command">{R}←⎕FUNTIE Y</div>
</div>

`Y` must be a simple integer scalar or vector (including Zilde).  Files whose tie numbers occur in `Y` are untied.  Other elements of `Y` have no effect.

If `Y` is empty, no files are untied, but all the interpreter's internal file buffers are flushed and the operating system is asked to flush all file updates  to disk.  This special facility allows the programmer to add extra security (at the expense of performance) for application data files.

The shy result of `⎕FUNTIE` is a vector of tie numbers of the files actually untied.

# Example
```apl
      ⎕FUNTIE ⎕FNUMS ⍝ Unties all tied files
 
      ⎕FUNTIE ⍬      ⍝ Flushes all buffers to disk
```
