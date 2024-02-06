<div class="heading">
  <div class="name">Make Directory</div>
  <div class="command">{R}←{X}⎕MKDIR Y</div>
</div>

This function creates new directories.

`Y` is a character vector or scalar containing a single directory name, or a vector of character vectors containing zero or more directory names. Names must conform to the naming rules of the host Operating System.

By default, for each file in `Y` the path must exist and the base name must not exist (see [File Name Parts on page 1](/nparts.md#NParts)), otherwise an error is signalled.

The optional left argument `X` is the numeric scalar 0, 1, 2 or 3 which amends this behaviour as shown in the following table. If omitted, it is assumed to be 0.

| `0` | Default behaviour. |
| --- | --- |
| `1` | No action is taken if a directory specified by `Y` already exists. The return value may be used to determine whether a new directory was created or not. |
| `2` | Any part of the **paths** specified in `Y` which does not already exist will be created in preparation of creating the corresponding directory. |
| `3` | Combination of 1 and 2. |

If `Y` specifies a single name, the shy result `R` is a scalar 1 if a directory was created or 0 if not. If `Y` is a vector of character vectors, `R` is a vector of 1s and 0s with the same length as `Y`.

# Examples
```apl

      ⎕NEXISTS '/Users/Pete/Documents/temp'
0
      ⎕←⎕MKDIR '/Users/Pete/Documents/temp'
1
      ⎕←⎕MKDIR '/Users/Pete/Documents/temp'
FILE NAME ERROR: Directory exists
      ⎕←⎕MKDIR'/Users/Pete/Documents/temp'
     ∧

      ⎕←⎕MKDIR'/Users/Pete/Documents/temp/t1/t2'
FILE NAME ERROR: Unable to create directory ("The system cannot find the path specified.")
      ⎕←⎕MKDIR'/Users/Pete/Documents/temp/t1/t2'
     ∧

      ⎕←2 ⎕MKDIR'/Users/Pete/Documents/temp/t1/t2'
1
      ⊢⎕MKDIR'temp1' 'temp2'
1 1

```

# Note

When multiple names are specified they are processed in the order given. If an error occurs at any point whilst creating directories, processing will immediately stop and an error will be signalled. The operation is not atomic; some directories may be created before this happens. In the event of an error there will be no result and therefore no indication of how many directories were created before the error occurred.
