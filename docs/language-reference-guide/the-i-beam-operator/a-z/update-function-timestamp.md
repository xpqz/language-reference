<div class="heading">
  <div class="name">Update Function Timestamp</div>
  <div class="command">{R}←X(1159⌶)Y</div>
</div>

`Y` is an array of function names in the same format as the right argument of `⎕AT`. For further information, see [Attributes on page 1](/system-functions/at.md#Attributes).

`X` is an array of function attributes in the same format as the output of `⎕AT`.

The shy result `R` is a vector of numeric items, one per each specified function containing the following values:

| `0` | No change was made; the name is not that of a function, or the function was locked |
| --- | --- |
| `1` | The time and user stamp were updated |

Note that the last item of the function timestamp must be set to 0 otherwise `1159 ⌶` will generate a `DOMAIN ERROR`. Additionally, the timestamp must be greater than `1970 1 1 0 0 0 0`.

# Example
```apl

      ]disp ⎕AT'Christmas'
┌→────┬───────────────────┬─┬───────┐
│0 0 0│2013 3 1 11 14 58 0│0│Richard│
└~───→┴~─────────────────→┴─┴───────┘
      
	  x←⎕AT 'Christmas'
      x[2 4]←(2012 12 25 11 59 0 0)('Santa')
      x (1159⌶) 'Christmas'
      
	  ]disp ⎕AT'Christmas'
┌→────┬────────────────────┬─┬─────┐
│0 0 0│2012 12 25 11 59 0 0│0│Santa│
└~───→┴~──────────────────→┴─┴────→┘
```
