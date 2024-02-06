<div class="heading">
  <div class="name">Windows Command Processor</div>
  <div class="command">)CMD cmd</div>
</div>

This command allows Windows Command Processor or UNIX shell commands to be given from APL.  `)CMD` is a synonym of `)SH`.  Either command may be given in either environment (Windows or UNIX) with exactly the same effect.  `)CMD` is probably more natural for the Windows user.  This section describes the behaviour of `)CMD` and `)SH` under Windows.  See ["Execute (UNIX) Command: " on page 1](/sh.md#Execute(UNIX)Command) for a discussion of the behaviour of these commands under UNIX.

Note that under Windows, you may not execute `)CMD` without a command.  If you wish to, you can easily open a new Command Prompt window outside APL.

# Example
```apl
     )cmd dir
 Volume in drive C is OS
 Volume Serial Number is B438-9B76

 Directory of C:\Users\Pete\Documents\Dyalog APL-64 17.0 Unicode Files

23/06/2018  15:59    <DIR>          .
23/06/2018  15:59    <DIR>          ..
23/06/2018  14:53           181,488 default.dlf
13/06/2018  20:13         1,262,296 def_uk.dse
14/06/2018  14:36           108,976 UserCommand20.cache
               3 File(s)      1,552,760 bytes
               2 Dir(s)  101,371,437,056 bytes free

```

If cmd issues prompts and expects user input, it is ESSENTIAL to explicitly redirect input and output to the console.  If this is done, APL detects the presence of a "`>`" in the command line and runs the command processor in a visible window and does not direct output to the pipe.  If you fail to do this your system will appear to hang because there is no mechanism for you to receive or respond to the prompt.

# Example
```apl
      )CMD DATE <CON >CON
```

(Command Prompt window appears)
Current date is Wed 19-07-1995Enter new date (dd-mm-yy): 20-07-95

(Command Prompt window disappears)

# Implementation Notes

The argument of )`CMD` is simply passed to the appropriate command processor for execution and its output is received using an *unnamed pipe*.

By default, `)CMD` will execute the string `('cmd.exe /c',Y)` where `Y` is the argument given to `)CMD`.  However, the implementation permits the use of alternative command processors as follows:

Before execution, the argument is prefixed and postfixed with strings defined by the APL parameters CMD_PREFIX and CMD_POSTFIX. The former specifies the name of your command processor and any parameters that it requires. The latter specifies a string which may be required. If CMD_PREFIX is not defined, it defaults to the name defined by the environment variable COMSPEC followed by "\c".  If COMSPEC is not defined, it defaults to COMMAND.COM or CMD.EXE as appropriate. If CMD_POSTFIX is not defined, it defaults to an empty vector.
