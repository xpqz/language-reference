<div class="heading">
  <div class="name">Exclusive File Tie</div>
  <div class="command">{R}←X ⎕FTIE Y</div>
</div>
# Access code 2

`Y` must be 0 or a simple 1 or 2 element integer vector containing an available file tie number to be associated with the file for further file operations, and an optional passnumber.  If the passnumber is omitted it is assumed to be zero.  The tie number must not already be associated with a share tied or exclusively tied file.

`X` must be a simple character scalar or vector which specifies the name of the file to be exclusively tied.  The file must be named in accordance with the operating system's conventions, and may be a relative or absolute pathname.

The file must exist and  the user must have write access to it.  It may not already be tied by another user.

# Automatic Tie Number Allocation

A tie number of 0 as argument to a create, share tie or exclusive tie operation, allocates the first (closest to zero) available tie number, and returns it as an explicit result. This allows you to simplify code. For example:

from:
```apl
      tie←1+⌈/0,⎕FNUMS ⍝ With next available number,
      file ⎕FTIE tie   ⍝ ... tie file.
```

to:
```apl
      tie←file ⎕FTIE 0 ⍝ Tie with first available number.
```

The shy result of `⎕FTIE` is the tie number of the file.

# Examples
```apl
      'SALES' ⎕FTIE 1
 
      '../budget/COSTS' ⎕FTIE  2
 
      '../budget/expenses' ⎕FTIE 0
3
```
