<div class="heading">
  <div class="name">Start UNIX Auxiliary Processor</div>
  <div class="command">{R}←X ⎕SH Y</div>
</div>

Used dyadically, `⎕SH` starts an Auxiliary Processor. The effect, as far as the APL user is concerned, is identical under both Windows and UNIX although there are differences in the method of implementation. `⎕SH` is a synonym of `⎕CMD` Either function may be used in either environment (UNIX or Windows) with exactly the same effect. This section describes the behaviour of `⎕SH` and `⎕CMD` under UNIX. See ["Start Windows Auxiliary Processor: " on page 1](/start-windows-auxiliary-processor.md#StartWindowsAuxiliaryProcessor) for a discussion of the behaviour of these system functions under Windows.

Although it is still possible for users to create their own APs, Dyalog strongly recommends creating shared libraries/DLLs instead.

`X` must be a simple character vector. `Y` may be a simple character scalar or vector, or a nested character vector.

`⎕SH` loads the Auxiliary Processor from the file named by `X` using a search-path defined by the environment variable WSPATH.

The shy result `R` is the process id of the Auxiliary Processor task.

The effect of starting an AP is that one or more external functions are defined in the workspace. These appear as locked functions and may be used in exactly the same way as regular defined functions.

When an external function is used in an expression, the argument(s) (if any) are piped to the AP for processing. If the function returns a result, APL halts while the AP is processing and waits for the result. If not it continues processing in parallel.

The syntax of dyadic `⎕SH` is similar to the UNIX execl(2) system call, where '`taskname`' is the name of the auxiliary processor to be executed and `arg0` through `argn` are the parameters of the calling line to be passed to the task, viz.
```apl

      'taskname' ⎕SH 'arg0' 'arg1' ... 'argn'

```

# Examples
```apl

      'xutils' ⎕SH 'xutils' 'ss' 'dbr'
      '/bin/sh' ⎕SH 'sh' '-c' 'adb test'
```
