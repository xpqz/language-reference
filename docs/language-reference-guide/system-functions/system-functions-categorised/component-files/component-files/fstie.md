<div class="heading">
  <div class="name">File Share Tie</div>
  <div class="command">{R}←X ⎕FSTIE Y</div>
</div>

`Y` must be 0 or a simple 1 or 2 element integer vector containing an available file tie number to be associated with the file for further file operations, and an optional passnumber.  If the passnumber is omitted it is assumed to be zero.  The tie number must not already be associated with a tied file.

`X` must be a simple character scalar or vector which specifies the name of the file to be tied.  The file must be named in accordance with the operating system's conventions, and may be specified with a relative or absolute pathname.

The file must exist and be accessible by the user.  If it is already tied by another task, it must not be tied exclusively.

The shy result of `⎕FSTIE` is the tie number of the file.

# Automatic Tie Number Allocation

A tie number of 0 as argument to a create, share tie or exclusive tie operation, allocates the first (closest to zero) available tie number and returns it as an explicit result. This allows you to simplify code. For example:

from:
```apl
      tie←1+⌈/0,⎕FNUMS  ⍝ With next available number,
      file ⎕FSTIE tie   ⍝ ... share tie file.
```

to:
```apl
      tie←file ⎕FSTIE 0 ⍝ Tie with 1st available number.
```

# Example
```apl
      'SALES' ⎕FSTIE 1
 
      '../budget/COSTS' ⎕FSTIE 2
```
