<div class="heading">
  <div class="name">Token Pool</div>
  <div class="command">R←⎕TPOOL</div>
</div>

`R` is a simple scalar or vector containing the token types for each of the tokens that are currently in the token pool.

The following (`⎕ML=0`) function returns a 2-column snapshot of the contents of the pool. It does this by removing and replacing all of the tokens, restoring the state of the pool exactly as before. Coding it as a single expression guarantees that `snap` is atomic and cannot disturb running threads.
```apl
      snap←{(⎕TGET ⍵){(⍉↑⍵ ⍺) ⊣ ⍺ ⎕TPUT¨⍵}⍵}
 
      snap ⎕TPOOL   snap ⎕TPOOL
┌────┬─────────┐
│1.1 │1.1      │
├────┼─────────┤
│1.2 │1.2      │
├────┼─────────┤
│1.3 │1.3      │
├────┼─────────┤
│¯1.9│ no limit│
└────┴─────────┘

```

See also: [Querying  the Token Pool (Y is 2) on page 1](/talloc.md#Querying).
