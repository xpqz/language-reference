<div class="heading">
  <div class="name">Manage RIDE Connections</div>
  <div class="command">R←3502⌶Y</div>
</div>

`3502⌶` gives control over RIDE connections to the interpreter. More details about RIDE can be found in the RIDE User Guide.

`Y` may be either `0` or `1` or a simple character vector.

`R` has the value `0` if the call to `3502⌶` was successful; if unsuccessful the value may be either a positive or negative integer.

If `Y` is `0`, then any active RIDE connections are disconnected, and no future connections may be made.

If `Y` is `1`, then the interpreter attempts to enable RIDE, using the value of the initialisation string to determine the connection details.  If the current initialisation string is ill-defined, `R` will be 64. If the Conga DLL/shared libraries are not available,  `R` will be 32. In previous versions of Dyalog there were separate RIDE and Conga DLLs/shared libraries; these have been merged into one set in 16.0.

If `Y` is a character vector and RIDE is currently disabled, then the current initialisation string is unconditionally replaced by the contents of `Y`. If RIDE is currently enabled, the initialisation string is not replaced, and `R` will have the value `¯2`.

The initialisation string has the same syntax as the value of the RIDE_INIT configuration parameter which is described in the RIDE User Guide

If RIDE is currently disabled, and `3502⌶0` is called or if RIDE is currently enabled and `3502⌶1` is called, no action is taken and `R` will have the value `¯1`.

The configuration parameter RIDE_INIT can still be used to establish the initial value of the RIDE initialisation string.

The runtime interpreter has RIDE disabled by default, whether or not RIDE_INIT is set; the only method of enabling RIDE in a runtime interpreter is to  call `3502⌶1`.

If RIDE_INIT is set when a development interpreter is called, RIDE will be enabled provided that the RIDE DLL/shared library is available and the RIDE_INIT variable is properly formed. If the connection is of type SERVE the port must not be in use.  If any of these conditions are not met, then the interpreter fails with a non-zero exit code.  If RIDE_INIT is not set then the development interpreter will start, but with RIDE disabled.

It is therefore possible to override the RIDE_INIT variable in the development interpreter with code similar to:
```apl

      r←3502⌶0             ⍝ Stop RIDE
      r←3502⌶'SERVE::4511' ⍝ Update init string
      r←3502⌶1             ⍝ Start RIDE
                          
```

And similarly for altering the RIDE settings in an active APL session.

# Notes:

In 14.1 and earlier `3502⌶⍬` was used to enable RIDE; this value is still valid, albeit deprecated: code should call `3502⌶1` instead.

Enabling the RIDE to access applications that use the run-time interpreter means that the APL code of those applications can be accessed. The I-beam mechanism described above means that the APL code itself must grant the right for a RIDE client to connect to the run‑time interpreter. Although Dyalog Ltd might change the details of this mechanism, the APL code will always need to grant connection rights. In particular, no mechanism that is only dependent on configuration parameters will be implemented.
