<div class="heading">
  <div class="name">Account Information</div>
  <div class="command">R←⎕AI</div>
</div>

This is a simple integer vector, whose four elements are:

| `⎕AI[1]` | user identification. Under Windows, this is the aplnid (network ID from configuration dialog box). Under UNIX and Linux this is the **effective** UID of the account whereas `⎕AN` returns the real name. |
| --- | --- |
| `⎕AI[2]` | compute time for the APL session in milliseconds. |
| `⎕AI[3]` | connect time for the APL session in milliseconds. |
| `⎕AI[4]` | keying time for the APL session in milliseconds. |

Elements beyond 4 are not defined but reserved.

# Example
```apl

     ⎕AI
52 7396 2924216 2814831
```
