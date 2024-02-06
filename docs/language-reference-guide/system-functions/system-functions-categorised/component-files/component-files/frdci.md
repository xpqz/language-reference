<div class="heading">
  <div class="name">File Read Component Information</div>
  <div class="command">R←⎕FRDCI Y</div>
</div>
# Access code 512

`Y` must be a simple integer vector of length 2 or 3 containing the file tie number, component number and an optional passnumber.  If the passnumber is omitted it is assumed to be zero.

The result is a 3 element numeric vector containing the following information:

1. the size of the component in bytes (i.e. how much disk space it occupies).
2. the user number of the user who last updated the component.
3. the time of the last update in 60ths of a second since 1st January 1970 (UTC).
# Example
```apl
      ⎕FRDCI 1 13
2200 207 3.702094494E10
```
