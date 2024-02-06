<div class="heading">
  <div class="name">Put Tokens</div>
  <div class="command">{R}←{X} ⎕TPUT Y</div>
</div>

`Y` must be a simple numeric scalar or vector of non-zero token types. Non-integer values in `Y` must fall within a range that has been allocated using `⎕TALLOC`.

`X` is an optional array of values to be stored in each of the tokens specified by `Y`.

Shy result `R` is a vector of thread numbers (if any) unblocked by the `⎕TPUT`.

# Examples
```apl
    ⎕TPUT 2 3 2       ⍝ put a 2-token, a 3-token and
                        another 2-token into the pool.
 
    88 ⎕TPUT 2        ⍝ put another 2-token into the pool
                        this token has the value 88.
 
    'Hello'⎕TPUT ¯1.9 ⍝ put a ¯1.9-token into the pool
                        with the value 'Hello'.
```

If `X` is omitted, the *value* associated with each of the tokens added to the pool is the same as its *type*.

Note that you cannot put a 0-token into the pool; 0-s are removed from `Y`.
