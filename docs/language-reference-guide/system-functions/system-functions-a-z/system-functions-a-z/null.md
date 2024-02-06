<div class="heading">
  <div class="name">Null Item</div>
  <div class="command">R←⎕NULL</div>
</div>

This is a reference to a null item, such as may be returned across the COM interface to represent a null value. A null might be returned as the result of a .NET method or as the value of an empty cell in a spreadsheet

`⎕NULL` may be used in any context that accepts a namespace reference, in particular:

- As the argument to a defined function
- As an item of an array.
- As the argument to those primitive functions that take character data arguments, for example: `=, ≠, ≡, ≢, ,, ⍴, ⊃, ⊂`
# Example
```apl
      'EX'⎕WC'OLEClient' 'Excel.Application'
      WB←EX.Workbooks.Open 'simple.xls'
 
      (WB.Sheets.Item 1).UsedRange.Value2
 [Null]  [Null]  [Null]  [Null]  [Null] 
 [Null]    Year  [Null]  [Null]  [Null] 
 [Null]    1999    2000    2001    2002 
 [Null]  [Null]  [Null]  [Null]  [Null] 
 Sales      100      76     120     150 
 [Null]  [Null]  [Null]  [Null]  [Null] 
 Costs       80      60     100     110 
 [Null]  [Null]  [Null]  [Null]  [Null] 
 Margin      20      16      20      40 
```

To determine which of the cells are filled, you can compare the array with `⎕NULL`.
```apl
      ⎕NULL≢¨(WB.Sheets.Item 1).UsedRange.Value2
0 0 0 0 0
0 1 0 0 0
0 1 1 1 1
0 0 0 0 0
1 1 1 1 1
0 0 0 0 0
1 1 1 1 1
0 0 0 0 0
1 1 1 1 1
```
