<div class="heading">
  <div class="name">Canonical Representation</div>
  <div class="command">R←180⌶Y</div>
</div>

This function is the same as the system function `⎕CR` except that it can be used to obtain the canonical representation of methods in classes. `180⌶` is used by `]PROFILE`.

# Example
```apl

      )load ComponentFile
C:\Program Files\Dyalog\Dyalog APL-64 15.0 Unicode\...

      180⌶'ComponentFile.Close'
 Close                          
 :Implements Destructor         
 :If tie∊⎕FNUMS                 
     :If temp ⋄ Name ⎕FERASE tie
     :Else ⋄ ⎕FUNTIE tie        
     :EndIf                     
 :EndIf                         
  
```
