# System Variables

System variables retain information used by the system in some way. Many system variables affect the behaviour of primitive functions and operators to which they act as**implicit arguments**[(see page 1).](/system-functions-categorised.md#System_Settings)For further information, see [System Settings on page 1](/system-settings.md#Implicit_Arguments).

System variables may be localised by inclusion in the header line of a defined function or in the argument list of the system function `⎕SHADOW`. When a system variable is localised, it retains its previous value until it is assigned a new one. This feature is known as "pass-through localisation".  The exception to this rule is `⎕TRAP`.

A system variable can never be undefined. Default values are assigned to all system variables in a clear workspace.

| Name | Description | Scope |
| --- | --- | --- |
| `⎕AVU` | Atomic Vector – Unicode | Namespace |
| `⎕CT` | Comparison Tolerance | Namespace |
| `⎕DCT` | Decimal Comp Tolerance | Namespace |
| `⎕DIV` | Division Method | Namespace |
| `⎕FR` | Floating-Point Representation | Namespace |
| `⎕IO` | Index Origin | Namespace |
| `⎕LX` | Latent Expression | Workspace |
| `⎕ML` | Migration Level | Namespace |
| `⎕PATH` | Search Path | Session |
| `⎕PP` | Print Precision | Namespace |
| `⎕PW` | Print Width | Session |
| `⎕RL` | Random Link | Namespace |
| `⎕RTL` | Response Time Limit | Namespace |
| `⎕SM` | Screen Map | Workspace |
| `⎕TNAME` | Thread Name | Workspace |
| `⎕TRAP` | Event Trap | Workspace |
| `⎕USING` | Microsoft .NET Search Path | Namespace |
| `⎕WSID` | Workspace ID | Workspace |
| `⎕WX` | Window Expose | Namespace |

In other words,  `⎕PATH` and `⎕PW` relate to the session.  `⎕LX`, `⎕SM`, `⎕TRAP` and `⎕WSID` relate to the active workspace.  All the other system variables relate to the current namespace.

| Session | Workspace | Namespace |
| --- | --- | --- |
| `⎕PATH` | `⎕LX` | `⎕AVU` |
| `⎕PW` | `⎕SM` | `⎕CT` |
| `` | `⎕TRAP` | `⎕DCT` |
| `` | `⎕WSID` | `⎕DIV` |
| `` | `` | `⎕FR` |
| `` | `` | `⎕IO` |
| `` | `` | `⎕ML` |
| `` | `` | `⎕PP` |
| `` | `` | `⎕RL` |
| `` | `` | `⎕RTL` |
| `` | `` | `⎕USING` |
| `` | `` | `⎕WX` |

Note that the value assigned to a system variable must be appropriate; otherwise an error will be reported immediately.

### Example
```apl
      ⎕IO←3
DOMAIN ERROR
      ⎕IO←3
      ^
```
