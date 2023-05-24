# GDB Commands

<div>
<table>
<tr><th>RUNNING</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| `gdb` <program> [core dump]           | Start GDB (with optional core dump).                |
| `gdb` --args <program> <args...>      | Start GDB and pass arguments                        |
| `gdb` --pid <pid>                     | Start GDB and attach to process.                    |
| `set args` <args...>                  | Set arguments to pass to program to be debugged.    |
| `run`                                 | Run the program to be debugged.                     |
| `kill`                                | Kill the running program.                           |
</td></tr> </table
</div>
  
<div>
<table>
<tr><th>BREAKPOINTS</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| `break` (line or function)                      | set a breakpoint on a line or function            |
| `break` main.c:42                               | set breakpoint at file and (line or function)     |
| `tbreak` (line or function)                     | set a temporary breakpoint                        |
| `watch` (variable)                              | set software watchpoint on variable               |
| `info breakpoints`                              | show breakpoints                                  |
| `info watchpoints`                              | show current watchpoints                          |
| `delete` (breakpoint number)                    | delete a breakpoint by number                     |
| `delete`                                        | delete all breakpoints (prompted)                 |
| `clear`                                         | delete breakpoints at current line                |
| `clear` (line or function)                      | delete breakpoints at line or function            |
| `disable` (breakpoint number)                   | turn a breakpoint off, but don't remove it        |
| `enable` (breakpoint number)                    | turn disabled breakpoint back on                  |
| `commands` (breakpoint number) (commands) `end` | set gdb commands with breakpoint                  |
| `ignore` (breakpoint number) (n times)          | ignore breakpoint n times before activation       |
| `condition` (breakpoint number) (expression)    | break only if expression is true                  |
| `condition` (breakpoint number) (condition)     | example: `condition 1 i == 2`                     |
| `condition` (breakpoint number)                 | delete condition at breakpoint number             |
  
</td></tr> </table
</div>
  
set follow-fork-mode <child or parent>










