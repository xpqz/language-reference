<div class="heading">
  <div class="name">Externalise Array</div>
  <div class="command">R←8674⌶Y</div>
</div>

This function creates an externalised array.

`Y` may be any array.

The result `R` is a copy of `Y` that has been created in a separate area of memory to that allocated to the active workspace.

This is an experimental function that may  improve the overall performance of an application by reducing workspace management activity.

Externalising an array isolates it from the dynamic workspace management process that occurs constantly as objects are created, modified and destroyed. Moving data around in memory consumes computing power. Removing a large nested constant from this  managed area guarantees that it will not be subjected to such movement and potentially reduces the amount of data shuffling entailed during a compaction which in turn may improve overall performance.

There is no link between `Y` and the externalised copy of `Y`. If `Y` is erased, the copy of `Y` referenced via `R` still exists, but outside the workspace. Indeed, there is no benefit to be gained by using this function unless the original array `Y` is expunged from in the workspace.

# Notes:

- This function is experimental and its effect is likely to be application dependent. There is no guarantee that it will  improve performance in every application.
- Little or no benefit is obtained by externalising small or simple arrays as they will typically become part of the sediment, a collection of objects in the workspace that  remains relatively stable.
- There is no benefit obtained in externalising an array that is going to change; indeed there will probably be a dis-benefit. There is a cost associated with externalising an array and a cost associated with changing an externalised array.

The **externalised** property of the array does survive `)SAVE`/`)LOAD` but not `0 ⎕SAVE`, `⎕CY`, `)COPY` or `)PCOPY`. Nor does it survive writing to a component file and reading back again.
