set follow-fork-mode <child or parent>

# GDB Commands

*(gdb) run        	run the program with current arguments
*(gdb) run args redirection        run with args and redirection
(gdb) set args args...        set arguments for run 
(gdb) show args        show current arguments to run
*(gdb) cont            continue the program
*(gdb) step            single step the program; step into functions
(gdb) step count       singlestep \fIcount\fR times
*(gdb) next            step but step over functions 
(gdb) next count       next \fIcount\fR times
*(gdb) CTRL-C          actually SIGINT, stop execution of current program 
*(gdb) attach process-id        attach to running program
*(gdb) detach        detach from running program
*(gdb) finish        finish current function's execution
(gdb) kill           kill current executing program

<div>
<table>
<tr><th>RUNNING?!</th>
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
<tr><th>HELP</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| `help`        	                        | list command classes |
| `help running`                          | list commands in one command class |
| `help run`        	                    | bottom-level help for a command "run" | 
| `help info`                             | list info commands (running program state) |
| `help info line`                        | help for a particular info comman |
| `help show`                             | list show commands (gdb state) |
| `help show commands`                    | specific help for a show comma |

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
  
<div>
<table>
<tr><th>STACK BACKTRACE</th>
<tr><td>
  
| Command | Result |
| :------ | :----- |
| (gdb) `bt`                  | print stack backtrace |
| (gdb) `frame`        	      | show current execution position |
| (gdb) `up`        	        | move up stack trace  (towards main) |
| (gdb) `down`        	      | move down stack trace (away from main) |
| (gdb) `info locals`         | print automatic variables in frame |
| (gdb) `info args`           | print function parameters | 

</td></tr> </table
</div>









