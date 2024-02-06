<div class="heading">
  <div class="name">Thread Identity</div>
  <div class="command">)TID {tid}</div>
</div>

`)TID` associates the Session window with the specified thread so that expressions that you subsequently execute in the Session are executed in the context of that thread.

If you attempt to `)TID` to a thread that is paused or running, that thread will, if possible, be interrupted by a strong interrupt. If the thread is in a state which it would be inappropriate to interrupt (for example, if the thread is executing an external function), the system reports:
```apl
      Can't switch, this thread is n
```

If no thread number is given, `)TID` reports the number of the current thread.

# Examples
```apl
      ⍝ State indicator
      )si
·   #.print[1]
&3
·   ·   #.sub_calc[2]*
·   &2
·   #.calc[1]
&1
 
      ⍝ Current thread
      )tid
is 2
 
      ⍝ Switch suspension to thread 3
      )tid 3
was 2
 
      ⍝ State indicator
      )si
·   #.print[1]*
&3
·   ·   #.sub_calc[2]
·   &2
·   calc[1]
&1
 
      ⍝ Attempt to switch to pendent thread 1
      )tid 1
Can't switch, this thread is 3
```
