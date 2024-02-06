<div class="heading">
  <div class="name">I-Beam</div>
  <div class="command">R←{X}(A⌶)Y</div>
</div>

I-Beam is a monadic operator that provides a range of system related services.

WARNING: Although documentation is provided for I-Beam functions, any service provided using I-Beam should be considered as "experimental" and subject to change – without notice - from one release to the next. Any use of I-Beams in applications should therefore be carefully isolated in cover-functions that can be adjusted if necessary. See also: [RIDE and Experimental Features-related I-Beams on page 1](/i-beam-functions/supplementary-i-beam-functions.md#NonCoreIBeams).

`A` is an integer that specifies the type of operation to be performed  as shown in the table below. `Y` is an array that supplies further information about what is to be done.

`X` may or may not be required depending on `A`.

`R` is the result of the derived function.

When attempting to use  I-Beam with an unsupported operation value, `A`, one of three different error messages will be reported:

- Invalid I-Beam function selection
- I-Beam function xxx has been withdrawn
- I-Beam function xxx is not supported by this interpreter

This allows the user to distinguish between operation values that have never been used, those that have been used in earlier versions but are no longer included in the current version, and those
that are valid in other editions or on other platforms other than the current interpreter.

The column labelled **O/S** indicates if a function applies only on Windows (W), only on Windows .NET Framework, (WF), only under IBM AIX (AIX), or only on non-Windows (X) platforms.

| A | Derived Function | O/S |
| --- | --- | --- |
| `8` | [Inverted Table Index-of](/i-beam-functions/inverted-table-index-of.md#) |  |
| `85` | [Execute Expression](/i-beam-functions/execute-expression.md#) |  |
| `127` | [Overwrite Free Pockets](/i-beam-functions/overwrite-free-pockets.md#) |  |
| `180` | [Canonical Representation](/i-beam-functions/canonical-representation.md#) |  |
| `181` | [Unsqueezed Type](/i-beam-functions/unsqueezed-type.md#) |  |
| `200` | [Syntax Colouring](/i-beam-functions/syntax-colouring.md#) |  |
| `201` | [Syntax Colour Tokens](/i-beam-functions/syntax-colour-tokens.md#) |  |
| `219` | [Compress/Decompress Vector of Short Integers](/i-beam-functions/compress-vector-of-short-integers.md#) |  |
| `220` | [Serialise/Deserialise Array](/i-beam-functions/serialise-array.md#) |  |
| `400` | [Compiler Control](/i-beam-functions/compiler-control.md#Compiler_Control) |  |
| `600` | [Trap Control](/i-beam-functions/trap-control.md#Trap_Control) |  |
| `739` | [Temporary Directory](/i-beam-functions/temporary-directory.md#Temporary_Directory) |  |
| `819` | [Case Convert](/i-beam-functions/case-convert.md#Case_Convert) |  |
| `900` | [Called Monadically](/i-beam-functions/called-monadically.md#Called_Monadically) |  |
| `950` | [Loaded Libraries](/i-beam-functions/loaded-libraries.md#Loaded_Libraries) |  |
| `1010` | [Set Shell Script Debug Options](/i-beam-functions/set-shell-script-debug-options.md#) |  |
| `1111` | [Number of Threads](/i-beam-functions/number-of-threads.md#) |  |
| `1112` | [Parallel Execution Threshold](/i-beam-functions/parallel-execution-threshold.md#) |  |
| `1159` | [Update Function Time and User Stamp](/i-beam-functions/update-function-timestamp.md#) |  |
| `1200` | [Format Date-time](/i-beam-functions/format-datetime.md#) |  |
| `1302` | [Set aplcore Parameters](/i-beam-functions/set-aplcore-parameters.md#) |  |
| `1500` | [Hash Array](/i-beam-functions/hash-array.md#) |  |
| `2000` | [Memory Manager Statistics](/i-beam-functions/memory-manager-statistics.md#) |  |
| `2002` | [Specify Workspace Available](/i-beam-functions/specify-workspace-available.md#) |  |
| `2007` | [Disable Global Triggers](/i-beam-functions/disable-global-triggers.md#Trigger_Control) |  |
| `2010` | [Update DataTable](/i-beam-functions/update-datatable.md#) | WF |
| `2011` | [Read DataTable](/i-beam-functions/read-datatable.md#) | WF |
| `2014` | [Remove Data Binding](/i-beam-functions/remove-data-binding.md#Remove_Data_Bindings) | WF |
| `2015` | [Create Data Binding Source](/i-beam-functions/create-data-binding-source.md#) | WF |
| `2016` | [Create .NET Delegate](/i-beam-functions/create-net-delegate.md#Identify_NET_Type) | WF |
| `2017` | [Identify .NET Type](/i-beam-functions/identify-net-type.md#Identify_NET_Type) | WF |
| `2022` | [Flush Session Caption](/i-beam-functions/flush-session-caption.md#Flush_Session_Caption) | W |
| `2023` | [Close all Windows](/i-beam-functions/close-all-windows.md#Close_all_Windows) |  |
| `2035` | [Set Dyalog Pixel Type](/i-beam-functions/set-dyalog-pixel-type.md#Set_Dyalog_Pixel_Type) | W |
| `2041` | [Override COM Default Value](/i-beam-functions/override-com-default-value.md#) | W |
| `2100` | [Export to Memory](/i-beam-functions/export-to-memory.md#) | W |
| `2101` | [Close .NET AppDomain](/i-beam-functions/close-net-appdomain.md#Close_.NET_AppDomain) | WF |
| `2250` | [Verify .NET Interface](/i-beam-functions/verify-net-interface.md#) |  |
| `2400` | [Set Workspace Save Options](/i-beam-functions/set-workspace-save-options.md#Set_Workspace_Save_Options) |  |
| `2401` | [Expose Root Properties](/i-beam-functions/expose-root-properties.md#ExposeRootPropertiesI-Beam) |  |
| `2501` | [Discard thread on exit](/i-beam-functions/discard-thread-on-exit.md#Discard_Thread_On_Exit) | W |
| `2502` | [Discard parked threads](/i-beam-functions/discard-parked-threads.md#Discard_Parked_Threads) | W |
| `2503` | [Mark Thread as Uninterruptible](/i-beam-functions/mark-thread-as-uninterruptible.md#) |  |
| `2520` | [Use Separate Thread For .NET](/i-beam-functions/use-separate-thread-for-net.md#Use_Separate_Thread_For_NET) | WF |
| `2704` | [Continue Autosave](/i-beam-functions/continue-autosave.md#Continue_Autosave) |  |
| `3002` | [Disable Component Checksum Validation](/i-beam-functions/disable-component-checksum-validation.md#Disable_Component_Checksum_Validation) |  |
| `3012` | [Enable Compression of Large Components](/i-beam-functions/enable-compression-of-large-components.md#Enable_LZ4_Frames) |  |
| `3500` | [Send Text to RIDE-embedded Browser](/i-beam-functions/send-text-to-ride-embedded-browser.md#SendTexttoRIDEembeddedBrowser) |  |
| `3501` | [Connected to the RIDE](/i-beam-functions/connected-to-the-ride.md#Connected_RIDE) |  |
| `3502` | [Manage RIDE Connections](/i-beam-functions/manage-ride-connections.md#Manage_RIDE_Connections) |  |
| `4000` | [Fork New Task](/i-beam-functions/fork-new-task.md#) | AIX |
| `4001` | [Change User](/i-beam-functions/change-user.md#) | X |
| `4002` | [Reap Forked Tasks](/i-beam-functions/reap-forked-tasks.md#) | AIX |
| `4007` | [Signal Counts](/i-beam-functions/signal-counts.md#) | X |
| `5171` | [Discard Source Information](/i-beam-functions/discard-source-information.md#Discard_Source_Information) |  |
| `5172` | [Discard Source Code](/i-beam-functions/discard-source-code.md#Discard_Source_Code) |  |
| `5176` | [List Loaded Files](/i-beam-functions/list-loaded-files.md#) |  |
| `5177` | [List Loaded File Objects](/i-beam-functions/list-loaded-file-objects.md#) |  |
| `5178` | [Remove Loaded File Object Info](/i-beam-functions/remove-loaded-file-object-info.md#) |  |
| `5179` | [Loaded File Object Info](/i-beam-functions/loaded-file-object-info.md#) |  |
| `7162` | [JSON Translate Name](/i-beam-functions/json-translate-name.md#) |  |
| `8415` | [Singular Value Decomposition](/i-beam-functions/singular-value-decomposition.md#) |  |
| `8674` | [Externalise Array](/i-beam-functions/externalise-array.md#) |  |
| `9468` | [Hash Table Size](/i-beam-functions/hash-table-size.md#Hash_Table_Size) |  |
| `9469` | [Lookup Table Size](/i-beam-functions/lookup-table-size.md#Lookup_Table_Size) |  |
| `16808` | [Sample Probability Distribution](/i-beam-functions/sample-probability-distribution.md#) |  |
| `50100` | [Line Count](/i-beam-functions/line-count.md#Line_Count) |  |
