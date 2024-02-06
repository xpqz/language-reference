<div class="heading">
  <div class="name">Specify Workspace Available</div>
  <div class="command">R←2002⌶Y</div>
</div>

This function is identical to the system function `⎕WA` except that it provides the means to specify the amount of memory The term **memory** here means virtual memory which includes memory mapped to disk.  that is *committed* for the workspace rather than have it assigned by the internal algorithm. Committed memory is memory that is allocated to a specific process and thereby reduces the amount of memory available for other applications.

Like `⎕WA`,  `2002⌶` compacts the workspace so that it occupies the minimum number of bytes possible, adds an *extra amount*, and then de-commits all the remaining memory that it is currently using, allowing it to be allocated by the operating system for use by other applications.

The argument `Y` is an integer which specifies the size, in bytes, of this *extra amount*.

The purpose of the *extra amount* is to reduce the likelihood that APL will immediately have to ask the operating system to re-commit memory that it has just de-committed, something that would have a deleterious effect on performance. At the same time, if the *extra amount* were to be excessively large, APL could  starve other applications of memory which itself could reduce the effective performance of the system. Whereas `⎕WA` calculates the size of the *extra amount* using a simple internal algorithm,  `2002⌶` uses a value specified by the programmer.

`R` is an integer which reports the size in bytes of the memory committed  for the workspace, and is the sum of the minimum amount required  by the workspace itself and the argument `Y`.

If the size of the committed workspace would be smaller than the minimum value (specified by `2000⌶`) or larger than the maximum value (which defaults to MAXWS), a `DOMAIN ERROR` is signalled.

See also [Memory Manager Statistics: on page 1](/memory-manager-statistics.md#MemoryManagerStatistics).

Note that this function does not change the size of the *extra amount* that will be applied subsequently by `⎕WA` or by an automatic compaction.
