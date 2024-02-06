<div class="heading">
  <div class="name">Execute (UNIX) Command</div>
  <div class="command">{R}←⎕SH Y</div>
</div>

`⎕SH` executes a UNIX shell or a Windows Command Processor.  `⎕SH` is a synonym of `⎕CMD`.  Either function may be used in either environment (UNIX or Windows) with exactly the same effect.  `⎕SH` is probably more natural for the UNIX user.  This section describes the behaviour of `⎕SH` and `⎕CMD` under UNIX.  See ["Execute Windows Command: " on page 1](/execute-windows-command.md#ExecuteWindowsCommand) for a discussion of the behaviour of these system functions under Windows.

`Y` must be a simple character scalar or vector representing a UNIX shell command.  `R` is a nested vector of character vectors.

`Y` may be any acceptable UNIX command. If the command does not produce any output, `R` is `0⍴⊂''` but the result is suppressed if not explicitly used or assigned.  If the command has a non-zero exit code, then APL will signal a `DOMAIN ERROR`.  If the command returns a result and has a zero exit code, then each element of `R` will be a line from the standard output (stdout) of the command.  Output from standard error (stderr) is not captured unless redirected to stdout.

# Examples
```apl
      ⎕SH'ls'
FILES WS temp
 
      ⎕SH 'rm WS/TEST'
 
      ⎕SH 'grep bin /etc/passwd ; exit 0'
bin:!:2:2::/bin:
 
      ⎕SH 'apl MYWS <inputfile >out1 2>out2 &'
```
