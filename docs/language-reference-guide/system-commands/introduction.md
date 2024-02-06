# Introduction

System commands are not executable APL expressions.  They provide services or information associated with the workspace and the external environment.

### Command Presentation

System commands may be entered from immediate execution mode or in response to the prompt `⎕`: within evaluated input.  All system commands begin with the symbol `)`, known as a right parenthesis.  All system commands may be entered in upper or lower case.

Each command is described in alphabetical order in this chapter.

System Commands

| Command | Description |
| --- | --- |
| `)CLASSES` | List classes |
| `)CLEAR` | Clear the workspace |
| `)CMD Y` | Execute a Windows Command |
| `)CONTINUE` | Save a Continue workspace and terminate APL |
| `)COPY {Y}` | Copy objects from another workspace |
| `)CS {Y}` | Change current namespace |
| `)DROP {Y}` | Drop named workspace |
| `)ED Y` | Edit object(s) |
| `)ERASE Y` | Erase object(s) |
| `)EVENTS` | List events of GUI namespace or object |
| `)FNS {Y}` | List user defined Functions |
| `)HOLDS` | Display Held tokens |
| `)LIB {Y}` | List workspaces in a directory |
| `)LOAD {Y}` | Load a workspace |
| `)METHODS` | List methods in GUI namespace or object |
| `)NS {Y}` | Create a global Namespace |
| `)OBJECTS {Y}` | List global namespaces |
| `)OBS {Y}` | List global namespaces (alternative form) |
| `)OFF` | Terminate the APL session |
| `)OPS {Y}` | List user defined Operators |
| `)PCOPY {Y}` | Perform Protected Copy of objects |
| `)PROPS` | List properties of GUI namespace or object |
| `)RESET` | Reset the state indicator |
| `)SAVE {Y}` | Save the workspace |
| `)SH {Y}` | Execute a (UNIX) Shell command |
| `)SI` | State Indicator |
| `)SIC` | Clear State Indicator |
| `)SINL` | State Indicator with local Name Lists |
| `)TID {Y}` | Switch current Thread Identity |
| `)VARS {Y}` | List user defined global Variables |
| `) WSID {Y}` | Workspace Identification |
| `)XLOAD Y` | Load a workspace; do not execute `⎕LX` |
| `{ }` indicates that the parameter(s) denoted by `Y` are optional. |

# System Commands (A-Z)

The remainder of this chapter describes the system commands one-by-one in alphabetical order.
