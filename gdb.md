# GDB Commands

<div>
<table>
<tr><th>RUNNING</th>
<tr><td>

| Command | Result |
| :---: | :--- |
| `gdb` <program> [core dump]           | Start GDB (with optional core dump).                |
| `gdb` --args <program> <args...>      | Start GDB and pass arguments                        |
| `gdb` --pid <pid>                     | Start GDB and attach to process.                    |
| `set args` <args...>                  | Set arguments to pass to program to be debugged.    |
| `run`                                 | Run the program to be debugged.                     |
| `kill`                                | Kill the running program.                           |
</td></tr> </table
</div>




Breakpoints
break <where>
Set a new breakpoint.
delete <breakpoint#>
Remove a breakpoint.
clear
Delete all breakpoints.
enable <breakpoint#>
Enable a disabled breakpoint.
disable <breakpoint#>
Disable a breakpoint.
