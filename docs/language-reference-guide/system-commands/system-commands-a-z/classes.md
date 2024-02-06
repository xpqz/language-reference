<div class="heading">
  <div class="name">List Classes</div>
  <div class="command">)CLASSES</div>
</div>

This command lists the names of APL Classes in the active workspace.

# Example:
```apl
      )CLEAR
clear ws
      )ED ○MyClass
 
:Class MyClass
    ∇ Make Name
      :Implements Constructor
      ⎕DF Name
    ∇
:EndClass ⍝ MyClass
 
      )CLASSES
MyClass
      )COPY OO YourClass
.\OO saved Sun Jan 29 18:32:03 2006
      )CLASSES
MyClass YourClass
      ⎕NC 'MyClass' 'YourClass'
9.4 9.4
```
