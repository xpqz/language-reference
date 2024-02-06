<div class="heading">
  <div class="name">Loaded Libraries</div>
  <div class="command">R←950⌶Y</div>
</div>

Reports the names of the dynamic link libraries that are currently loaded as a result of executing `⎕NA`.

`Y` is an empty vector.

The result `R` is a vector of character vectors containing  the names of all the DLLs or shared libraries that have been explicitly loaded by `⎕NA` and are still loaded by virtue of the presence of at least one external function reference.

# Examples
```apl
      )clear
clear ws
      'Aloc'⎕NA'P kernel32∣GlobalAlloc U4 P'
      'Free'⎕NA'P kernel32∣GlobalFree P'
      'Lock'⎕NA'P kernel32∣GlobalLock P'
      'Ulok'⎕NA'U4 kernel32∣GlobalUnlock P'
      'Valu'⎕NA'U4 version∣VerQueryValue* P <0T >U4 >U4'
      'copy'⎕NA'P msvcrt∣memcpy >U4[] P U4'
 
      950⌶⍬
 KERNEL32.DLL  VERSION.DLL  MSVCRT.DLL 
      )fns
Aloc    Free    Lock    Ulok    Valu    copy

      )erase Aloc    Free    Lock    Valu 
      950⌶⍬
 KERNEL32.DLL  MSVCRT.DLL 
      )fns
Ulok    copy

      )erase Ulok
      950⌶⍬
 MSVCRT.DLL 

      )clear
clear ws
      950⌶⍬

```
