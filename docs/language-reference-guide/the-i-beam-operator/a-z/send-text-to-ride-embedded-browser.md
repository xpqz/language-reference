<div class="heading">
  <div class="name">Send Text to RIDE-embedded Browser</div>
  <div class="command">R←{X}(3500⌶)Y</div>
</div>

Optionally, `X` is a simple character vector or scalar, the contents of which are used as the caption for the tab in the RIDE client that contains the embedded browser. If omitted, then the caption defaults to "`3500⌶`".

`Y` is a simple character vector the contents of which are displayed in the embedded browser tab.

To include SVG content, the HTML text in `Y` must include the following:

 <meta http-equiv="X-UA-Compatible" content="IE=9" >.

The result `R` identifies whether the write to the RIDE was successful. Possible values are:

- `0` : the write to the RIDE client was successful
- `¯1` : the write to the RIDE client was not successful
