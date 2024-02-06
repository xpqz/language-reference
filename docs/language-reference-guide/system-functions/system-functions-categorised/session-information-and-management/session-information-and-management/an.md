<div class="heading">
  <div class="name">Account Name</div>
  <div class="command">R←⎕AN</div>
</div>

This is a simple character vector containing the user (login) name. Under UNIX and Linux this is the real user name, whereas `⎕AI` returns the effective user id.

# Example
```apl
      ⎕AN
Pete
 
      ⍴⎕AN
4
```
