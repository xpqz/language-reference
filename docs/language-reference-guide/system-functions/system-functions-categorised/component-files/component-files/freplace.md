<div class="heading">
  <div class="name">File Replace Component</div>
  <div class="command">{R}←X ⎕FREPLACE Y</div>
</div>
# Access code 16

`Y` must be a simple 2 or 3 element integer vector containing the file tie number, the component number, and an optional passnumber.  If the passnumber is omitted it is assumed to be zero.  The component number specified must lie within the file's component number limits.

`X` is any array (including, for example, the `⎕OR` of a namespace), and overwrites the value of the specified component.  The component information (see ["File Read Component Information: " on page 1](/frdci.md#FileReadComponentInformation)) is also updated.

The shy result of `⎕FREPLACE` is the file index (component number of replaced record).

# Example
```apl
      SALES←⎕FREAD 1 241
 
      (SALES×1.1) ⎕FREPLACE 1 241
```

Define a function to replace (index, value) pairs in a component file JMS.DCF:
```apl
Frep←{
    tie←⍺ ⎕FTIE 0
    _←{⍵ ⎕FREPLACE tie ⍺}/¨⍵
    ⎕FUNTIE tie
} 
 
      'jms'Frep(3 'abc')(29 'xxx')(7 'yyy')
```
