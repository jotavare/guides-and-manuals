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
| (gdb) `break` (line or function)                      | set a breakpoint on a line or function            |
| (gdb) `break` main.c:42                               | set breakpoint at file and (line or function)     |
| (gdb) `tbreak` (line or function)                     | set a temporary breakpoint                        |
| (gdb) `watch` <variable>                              | set software watchpoint on variable               |
| (gdb) `info breakpoints`                              | show breakpoints                                  |
| (gdb) `info watchpoints`                              | show current watchpoints                          |
| (gdb) `delete` (breakpoint number)                    | delete a breakpoint by number                     |
| (gdb) `delete`                                        | delete all breakpoints (prompted)                 |
| (gdb) `clear`                                         | delete breakpoints at current line                |
| (gdb) `clear` (line or function)                      | delete breakpoints at line or function            |
| (gdb) `disable` (breakpoint number)                   | turn a breakpoint off, but don't remove it        |
| (gdb) `enable` (breakpoint number)                    | turn disabled breakpoint back on                  |
| (gdb) `commands` <breakpoint number> <commands> `end` | set gdb commands with breakpoint                  |
| (gdb) `ignore` <breakpoint number> <n times>          | ignore breakpoint n times before activation       |
| (gdb) `condition` <breakpoint number> <expression>    | break only if expression is true                  |
| (gdb) `condition` <breakpoint number> <condition>     | example: `condition 1 i == 2`                     |
| (gdb) `condition` <breakpoint number>                 | delete condition at breakpoint number             |
  
</td></tr> </table
</div>










