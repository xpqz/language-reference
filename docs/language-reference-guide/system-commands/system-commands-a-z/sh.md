<div class="heading">
  <div class="name">Execute (UNIX) Command</div>
  <div class="command">)SH {cmd}</div>
</div>

This command allows WINDOWS or UNIX shell commands to be given from APL.  `)SH` is a synonym of `)CMD`. Either command may be given in either environment (Windows or UNIX) with exactly the same effect.  `)SH` is probably more natural for the UNIX user. This section describes the behaviour of `)SH` and `)CMD` under UNIX. See ["Windows Command Processor: " on page 1](/cmd.md#WindowsCommandProcessor) for a discussion of their behaviour under Windows.

`)SH` allows UNIX shell commands to be given from APL. The argument must be entered in the appropriate case (usually lower-case).  The result of the command, if any, is displayed.

`)SH` causes Dyalog APL to invoke the system() library call. The shell which is used to run the command is therefore the shell which system() is defined to call. For example, under AIX this would be /usr/bin/sh.

When the shell is closed, control returns to APL. See *Dyalog for UNIX UI Guide* for further information.

The parameters CMD_PREFIX and CMD_POSTFIX may be used to execute a different shell under the shell associated with system().

# Example
```apl

      )sh ps -u andys | grep -v ps
   UID      PID    TTY  TIME CMD
  6179  9437326  pts/0  0:00 ksh
  6179 10223736  pts/0  0:00 dyalog
  6179 10354810  pts/0  0:00 sh
  6179 10879188  pts/0  0:00 ksh
  6179 11665660      -  0:00 sshd
```
