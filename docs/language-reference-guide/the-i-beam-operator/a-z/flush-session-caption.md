<div class="heading">
  <div class="name">Flush Session Caption</div>
  <div class="command">R←2022⌶Y</div>
</div>

Under Windows, the Session Caption displays information such as the name of the current workspace. The contents of the Caption can be modified: see **Window Captions** in the **Installation and Configuration Guide** for more details.

However, the Caption is updated only at the six-space prompt; calling `⎕LOAD` for example from within a function will not result in the Caption being updated at the end of the `⎕LOAD`.

This I-Beam causes the Session Caption to be updated (flushed) when called. Note that this I-Beam does not alter the contents of the Caption.

# Example
```apl

      2022⌶0    
```
