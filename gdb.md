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
| `break` main                         | set a breakpoint on a function                     |
| `break` 42                            | set a breakpoint on a function                    |
| `break` main.c:42                     | set breakpoint at file and line (or function)     |
  
</td></tr> </table
</div>

*(gdb) break basic.c:101        set breakpoint at file and line (or function)
*(gdb) info breakpoints        show breakpoints
*(gdb) delete 1         delete a breakpoint by number
(gdb) delete        	delete all breakpoints (prompted)
(gdb) clear             delete breakpoints at current line
(gdb) clear function    delete breakpoints at function
(gdb) clear line        delete breakpoints at line
(gdb) disable 2         turn a breakpoint off, but don't remove it
(gdb) enable 2          turn disabled breakpoint back on
(gdb) tbreak function|line        set a temporary breakpoint
(gdb) commands break-no ... end   set gdb commands with breakpoint
(gdb) ignore break-no count       ignore bpt N-1 times before activation
(gdb) condition break-no expression         break only if condition is true
(gdb) condition 2 i == 20         example: break on breakpoint 2 if i equals 20
(gdb) watch expression        set software watchpoint on variable
(gdb) info watchpoints        show current watchpoints








