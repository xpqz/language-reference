<div class="heading">
  <div class="name">Key Label</div>
  <div class="command">R←⎕KL Y</div>
</div>

`Y` is a simple character vector or a vector of character vectors containing Input Codes for Keyboard Shortcuts. In the Classic Edition, keystrokes are associated with Keyboard Shortcuts by the Input Translate Table.

`R` is a simple character vector or a vector of character vectors containing the labels associated with the codes.  If `Y` specifies codes that are not defined, the corresponding elements of `R` are the codes in `Y`.

`⎕KL` provides the information required to build device-independent help messages into applications, particularly full-screen applications using `⎕SM` and `⎕SR`.

# Examples:
```apl
      ⎕KL 'RC'
Right
 
      ⎕KL 'ER' 'EP' 'QT' 'F1' 'F13'
  Enter  Esc  Shift+Esc  F1  Shift+F1
```
