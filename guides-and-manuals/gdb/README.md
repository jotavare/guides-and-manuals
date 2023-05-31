# GDB Commands

- [100 GDB Tips](https://github.com/hellogcc/100-gdb-tips)
- [GDB Dashboard](https://github.com/cyrus-and/gdb-dashboard)
- [PDF GDB Cheetsheat](https://raw.githubusercontent.com/hellogcc/100-gdb-tips/master/refcard.pdf)
- [GitHub GDB Cheetsheat](https://gist.github.com/rkubik/b96c23bd8ed58333de37f2b8cd052c30)

|    | Definition                |
| :- | :------------------------ |
| 🟢 | Most used commands by me  |                 |
| 🔵 | Least used commands by me |

<div>
<table>
<tr><th>RUNNING THE PROGRAM</th>
<tr><td>
  
|    | Command                               | Result                                             |
| :- | :------------------------------------ | :------------------------------------------------- |
| 🟢 | `gdb`        		                     | Start gdb.                                         |
| 🟢 | `gdb --tui [object]`                  | Start gdb with graphic interface.                  |
| 🔵 | `gdb -silent`                         | Start gdb without the beginning information.       |
| 🟢 | `gdb -statistics`                     | Print statistics about time and memory usage.      |
| 🟢 | `gdb [object]`      	                 | Normal debug.                                      |
| 🔵 | `gdb [object] [core]` 	               | core debug (must specify core file).               |
| 🟢 | `gdb [object] [pid]`  	               | Attach to running process.                         |
| 🔵 | `gdb [program] [core dump]`           | Start GDB (with optional core dump).               |
| 🟢 | `gdb --args [program] [args...]`      | Start GDB and pass arguments.                      |
| 🟢 | `gdb --pid [pid]`                     | Start GDB and attach to process.                   |
| 🟢 | `run`                                 | Run the program with current arguments.            |
| 🔵 | `run [args] [redirection]`            | Run with args and redirection.                     |
| 🟢 | `set args [args...]`                  | Set arguments for run.                             |
| 🟢 | `show args`                           | Show current arguments to run.                     |
| 🔵 | `cont`                                | Continue the program.                              |
| 🟢 | `step`                                | Single step the program, also step into functions. |
| 🟢 | `step [number of lines]`              | Step n number of lines.                            |
| 🟢 | `next`                                | Next line.                                         |
| 🟢 | `next [number of lines]`              | Next n number of lines.                            |
| 🟢 | `attach [process-id]`                 | Attach to running program.                         |
| 🟢 | `detach`                              | Detach from running program.                       |
| 🔵 | `define [command ...] end`            | Define user command.                               |
| 🔵 | `RETURN`                              | Repeat last command.                               |
| 🔵 | `shell [command] [args]`              | Execute shell command.                             |
| 🔵 | `source [file]`                       | Load gdb commands from file.                       |
| 🟢 | `quit`                                | Quit gdb.                                          |
| 🟢 | `finish`                              | Finish current function's execution.               |
| 🟢 | `kill`                                | Kill current executing program.                    |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>HELP</th>
<tr><td>

|    | Command                                 | Result                                                 |
| :- | --------------------------------------- | ------------------------------------------------------ |
| 🔵 | `help` or `-h`                          | List command classes.                                  |
| 🔵 | `help running`                          | List commands in the "running" command class.          |
| 🔵 | `help run`                              | Bottom-level help for the command "run".               |
| 🔵 | `help info`                             | List info commands for examining program state.        |
| 🔵 | `help info line`                        | Help for the "info line" command.                      |
| 🔵 | `help show`                             | List show commands for displaying GDB state.           |
| 🔵 | `help show commands`                    | Specific help for the "show commands" command.         |

</td></tr>
</table>
</div>  

<div>
<table>
<tr><th>LAYOUT</th>
<tr><td>

|    | Command                                 | Result                                                                                  |
| :- | --------------------------------------- | --------------------------------------------------------------------------------------- |
| 🔵 | `layout next`                           | Display the next layout.                                                                |
| 🔵 | `layout prev`                           | Display the previous layout.                                                            |
| 🟢 | `layout src`                            | Display the source window only.                                                         |
| 🟢 | `layout asm`                            | Display the assembly window only.                                                       |
| 🟢 | `layout split`                          | Display the source and assembly window.                                                 |
| 🟢 | `layout regs`                           | Display the register window together with the source or assembly window.                |
| 🔵 | `focus next`                            | Make the next window active for scrolling.                                              |
| 🔵 | `focus prev`                            | Make the previous window active for scrolling.                                          |
| 🔵 | `focus src`                             | Make the source window active for scrolling.                                            |
| 🔵 | `focus asm`                             | Make the assembly window active for scrolling.                                          |
| 🔵 | `focus regs`                            | Make the register window active for scrolling.                                          |
| 🔵 | `focus cmd`                             | Make the command window active for scrolling.                                           |
| 🔵 | `refresh`                               | Refresh the screen. This is similar to typing `CTRL` + `L`.                             |
| 🔵 | `tui reg float`                         | Show the floating point registers in the register window.                               |
| 🔵 | `tui reg general`                       | Show the general registers in the register window.                                      |
| 🔵 | `tui reg system`                        | Show the system registers in the register window.                                       |
| 🔵 | `tui reg next`                          | Show the next register group. The list of register groups as well as their order.       |
| 🔵 | `update`                                | Update the source window and the current execution point.                               |
| 🟢 | `info win`                              | List and give the size of all displayed windows.                                        |
| 🟢 | `winheight [layout] [+-number]`         | Change the height of the window name by lines (+ increase and - decreases).             |
| 🔵 | `tabset [nchars]`                       | Set the width of tab stops to be nchars characters.                                     |
| 🔵 | `set height lpp`                        | Specify a screen height of lpp lines.                                                   |
| 🔵 | `show height`                           | Show current screen height.                                                             |
| 🔵 | `set width cpl`                         | Specify a screen width of cpl characters.                                               |
| 🔵 | `show width`                            | Show current screen width.                                                              |
| 🔵 | `tui reg float`                         | Show the floating point registers in the register window.                               |
| 🔵 | `tui reg system`                        | Show the system registers in the register window.                                       |
| 🔵 | `tui reg general`                       | Show the general registers in the register window.                                      |
| 🔵 | `set pagination [on] [off]`             | Turn the output pagination on or off. Turning pagination off = `set height 0`           |
| 🔵 | `show pagination`                       | Show the current pagination mode.                                                       |
| 🔵 | `set tui border-kind [kind]`            | Select the border appearance for the source, assembly and register windows.             |
| 🔵 | `[space]`                                 | Use a space character to draw the border.                                               |
| 🔵 | `[ascii]`                                 | Use ascii characters ‘+’, ‘-’ and ‘|’ to draw the border.                               |
| 🔵 | `[acs]`                                   | Use the Alternate Character Set to draw the border.                                     |
| 🔵 | `[drawn]`                                 | Using character line graphics if the terminal supports them.                            |
| 🔵 | `set tui border-mode [mode]`            | Select the display attributes for the inactive window border.                           |
| 🔵 | `set tui active-border-mode [mode]`     | Select the display attributes for the active window border.                             |
| 🔵 | `[standout]`                              | Use standout mode.                                                                      |
| 🔵 | `[reverse]`                               | Use reverse video mode.                                                                 |
| 🔵 | `[half]`                                  | Use half bright mode.                                                                   |
| 🔵 | `[half-standout]`                         | Use half bright and standout mode.                                                      |
| 🔵 | `[bold]`                                  | Use extra bright or bold mode.                                                          |
| 🔵 | `[bold-standout]`                         | Use extra bright or bold and standout mode.                                             |
  
</td></tr>
</table>
</div>
  
<div>
<table>
<tr><th>KEYBOARD SHORTCUTS</th>
<tr><td>
  
|    | Shortcut             | Result                                                   |
| -- | -------------------- | -------------------------------------------------------- |
| 🟢 | `CTRL` + `X` + `A`   | Enter or leave the TUI mode.                             |
| 🟢 | `CTRL` + `X` + `1`   | Use a TUI layout with only one window.                   |
| 🟢 | `CTRL` + `X` + `2`   | Use a TUI layout with at least two windows.              |
| 🟢 | `CTRL` + `X` + `O`   | Change the active window (use scrolling and arrow keys). |
| 🔵 | `PAGEUP`             | The active window one page up.                           |
| 🔵 | `PAGEDOWN`           | The active window one page down.                         |
| 🔵 | `UP`                 | The active window one line up.                           |
| 🔵 | `DOWN`               | The active window one line down.                         |
| 🔵 | `LEFT`               | The active window one column left.                       |
| 🔵 | `RIGHT`              | The active window one column right.                      |
| 🟢 | `CTRL` + `C`         | Actually SIGINT, stop execution of current program.      |
| 🟢 | `CTRL` + `L`         | Refresh the screen.                                      |
| 🟢 | `CTRL` + `P`         | Previous command.                                        |
| 🟢 | `CTRL` + `N`         | Next command.                                            |
| 🟢 | `CTRL` + `B`         | Move left in the command text.                           |
| 🟢 | `CTRL` + `F`         | Move right in the command text.                          |
| 🔵 | `ESC` + `CTRL` + `J` | Switch to vi edit mode from emacs edit mode.             |
  
</td></tr>
</table>
</div>

<div>
<table>
<tr><th>SINGLE KEY MODE</th>
<tr><td>

|    | Shortcut                   | Result                          |
| -- | -------------------------- | ------------------------------- |
| 🔵 | `CTRL` + `X` + `S`         | Switch to single key mode.      |
| 🔵 | `q`                        | Exit the SingleKey mode.        |
| 🔵 | `c`                        | continue                        |
| 🔵 | `d`                        | down                            |
| 🔵 | `f`                        | finish                          |
| 🔵 | `n`                        | next                            |
| 🔵 | `r`                        | run                             |
| 🔵 | `s`                        | step                            |
| 🔵 | `u`                        | up                              |
| 🔵 | `v`                        | info locals                     |
| 🔵 | `w`                        | where                           |
  
</td></tr>
</table>
</div>

<div>
<table>
<tr><th>BREAKPOINTS AND WATCHPOINTS</th>
<tr><td>

|    | Command                                                      | Result                                                      |
| :--| ------------------------------------------------------------ | ----------------------------------------------------------- |
| 🟢 | `break [line or function]`                                   | Set a breakpoint on a line or function.                     |
| 🔵 | `break main.c:42`                                            | Set breakpoint at file and (line or function).              |
| 🔵 | `tbreak [line or function]`                                  | Set a temporary breakpoint.                                 |
| 🟢 | `watch [variable]`                                           | Set a software watchpoint on a variable.                    |
| 🟢 | `info breakpoints`                                           | Show breakpoints and watchpoints.                           |
| 🔵 | `info watchpoints`                                           | Show current watchpoints.                                   |
| 🟢 | `delete [breakpoint or watchpoint number]`                   | Delete a breakpoint or watchpoint by number.                |
| 🟢 | `delete`                                                     | Delete all breakpoints and watchpoints (prompted).          |
| 🟢 | `clear`                                                      | Delete breakpoints and watchpoints at the current line.     |
| 🟢 | `clear [line or function]`                                   | Delete breakpoints or watchpoints at a line or function.    |
| 🟢 | `disable [breakpoint or watchpoint number]`                  | Turn a breakpoint or watchpoint off, but don't remove it.   |
| 🟢 | `enable [breakpoint or watchpoint number]`                   | Turn a disabled breakpoint or watchpoint back on.           |
| 🔵 | `commands [breakpoint or watchpoint number] [commands] end`  | Set GDB commands with a breakpoint or watchpoint.           |
| 🔵 | `ignore [breakpoint or watchpoint number] [n times]`         | Ignore a breakpoint or watchpoint n times before activation.|
| 🔵 | `condition [breakpoint or watchpoint number] [expression]`   | End only if the expression is true.                         |
| 🔵 | `condition [breakpoint or watchpoint number] [condition]`    | End only if the condition is true.                          |
| 🔵 | `condition [breakpoint or watchpoint number]`                | Delete condition at a breakpoint or watchpoint number.      |
  
</td></tr>
</table>
</div>
  
<div>
<table>
<tr><th>STACK BACKTRACE</th>
<tr><td>
  
|    | Command         | Result                                  |
| :- | --------------- | --------------------------------------- |
| 🟢 | `bt`            | Print stack backtrace.                  |
| 🔵 | `frame`         | Show current execution position.        |
| 🔵 | `up`            | Move up stack trace (towards main).     |
| 🔵 | `down`          | Move down stack trace (away from main). |
| 🟢 | `info locals`   | Print automatic variables in frame.     |
| 🟢 | `info args`     | Print function parameters.              |

</td></tr>
</table>
</div>
  
<div>
<table>
<tr><th>BROWSING SOURCE</th>
<tr><td>

|    | Command                      | Result                                              |
| :- | :--------------------------- | :-------------------------------------------------- |
| 🔵 | `list [20]`                  | List 10 lines around line `20`.                     |
| 🔵 | `list [1,10]`                | List lines `1` to `10`.                             |
| 🔵 | `list [main]`                | List lines around function `main`.                  |
| 🔵 | `list [basic.c:main]`        | List from another file `basic.c`.                   |
| 🔵 | `list -`                     | List previous 10 lines.                             |
| 🟢 | `info address [Symbol name]` | Displays the address of a given symbol.             |
| 🔵 | `list [*0x22e4]`             | List source at address `p0x22e4`.                   |
| 🔵 | `cd [dir]`                   | Change current directory to `dir`.                  |
| 🔵 | `pwd`                        | Print working directory.                            |
| 🔵 | `search regexpr`             | Forward search for regular expression `regexpr`.    |
| 🔵 | `reverse-search regexpr`     | Backward search for regular expression `regexpr`.   |
| 🔵 | `dir [dirname]`              | Add directory `dirname` to source path.             |
| 🔵 | `dir`                        | Reset source path to nothing.                       |
| 🔵 | `show directories`           | Show source path.                                   |

</td></tr>
</table>
</div>  

<div>
<table>
<tr><th>BROWSING DATA</th>
<tr><td>

|    | Command                         | Result                                         |
| :- | :------------------------------ | :--------------------------------------------- |
| 🟢 | `print [expression]`            | Print variable, added to value history.        |
| 🟢 | `print/x [expression]`          | Print variable in hex format.                  |
| 🔵 | `print [array[i]@count]`        | Artificial array - print array range.          |
| 🔵 | `print $`        	             | Print last value.                              |
| 🔵 | `print *$->next`                | Print thru history list.                       |
| 🔵 | `print $1`        	             | Print value 1 from value history.              |
| 🔵 | `print ::gx`                    | Force scope to be global.                      |
| 🔵 | `print [basic.c]::gx`           | Global scope in named file.                    |
| 🔵 | `print/x [&main]`               | Print address of function.                     |
| 🔵 | `x/countFormatSize [address]`   | Low-level examine command.                     |
| 🔵 | `x/x [&gx]`        	           | Print gx in hex.                               |
| 🔵 | `x/4wx [&main]`                 | Print 4 longs at start of main in hex format.  |
| 🔵 | `x/gf [&gd1]`                   | Print double.                                  |
| 🔵 | `help x`        	               | Show formats for x.                            |
| 🟢 | `info locals`                   | Print local automatics only.                   |
| 🟢 | `info functions regexp`         | Print function names.                          |
| 🟢 | `info variables regexp`         | Print global variable names.                   |
| 🟢 | `ptype [expression]`            | Print type definition.                         |
| 🟢 | `whatis [expression]`           | Print type of expression.                      |
| 🟢 | `set [variable] = [expression]` | Assign value.                                  |
| 🟢 | `display [expression]`          | Display expression result at stop.             |
| 🔵 | `undisplay`                     | Delete displays.                               |
| 🟢 | `info display`                  | Show displays.                                 |
| 🟢 | `show values`                   | Print value history.                           |
| 🟢 | `info history`                  | Print value history.                           |

</td></tr>
</table>
</div>  

<div>
<table>
<tr><th>OBJECT FILE MANIPULATION</th>
<tr><td>

|    | Command                  | Result                               |
| :- | :----------------------- | :----------------------------------- |
| 🔵 | `file [object]`      		| load new file for debug (sym+exec)   |
| 🔵 | `file`             		  | discard sym+exec file info           |
| 🔵 | `symbol-file [object]`   | load only symbol table               |
| 🔵 | `exec-file [object]` 		| specify object to run (not sym-file) |
| 🔵 | `core-file [core]`   		| post-mortem debugging                |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>SIGNAL CONTROL</th>
<tr><td>

|    | Command                  | Result                                    |
| :- | :----------------------- | :---------------------------------------- |
| 🟢 | `info signals`        	  | Print signal setup.                       |
| 🔵 | `handle signo actions`   | Set debugger actions for signal.          |
| 🔵 | `handle INT print`       | Print message when signal occurs.         |
| 🔵 | `handle INT noprint`     | Don't print message.                      |
| 🔵 | `handle INT stop`      	| Stop program when signal occurs.          |
| 🔵 | `handle INT nostop`      | Don't stop program.                       |
| 🔵 | `handle INT pass`       	| Allow program to receive signal.          |
| 🔵 | `handle INT nopass`      | Debugger catches signal; program doesn't. |
| 🔵 | `signal signo`        	  | Continue and send signal to program.      |
| 🔵 | `signal 0`               | Continue and send no signal to program.   |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>MACHINE-LEVEL DEBUG</th>
<tr><td>

|    | Command                  | Result                                          |
| :- | :----------------------- | :---------------------------------------------- |
| 🟢 | `info registers`        	| Print registers sans floats.                    |
| 🟢 | `info all-registers`     | Print all registers.                            |
| 🔵 | `print/x [$pc]`          | Print one register.                             |
| 🔵 | `stepi`        		      | Single step at machine level.                   |
| 🔵 | `nexti`        		      | Single step (over functions) at machine level.  |
| 🔵 | `display/i [$pc]`        | Print current instruction in display.           |
| 🔵 | `x/x [&gx]`        	    | Print variable gx in hex.                       |
| 🟢 | `info line [42]`         | Print addresses for object code for line 42.    |
| 🟢 | `info line [*0x2c4e]`    | Print line number of object code at address.    |
| 🔵 | `x/10i [main]`           | Disassemble first 10 instructions in main.      |
| 🔵 | `disassemble [address]`  | Dissassemble code for function around address.  |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>HISTORY DISPLAY</th>
<tr><td>

|    | Command                                     | Result                                                                                               |
| :- | :------------------------------------------ | :--------------------------------------------------------------------------------------------------- |
| 🟢 | `show commands`                             | Print command history.                                                                               |
| 🔵 | `info editing`       	                     | Print command history.                                                                               |
| 🔵 | `set history filename [fname]`              | Set the name of the GDB command history file to fname.                                               |
| 🔵 | `set history save`                          | Record command history in a file.                                                                    |
| 🔵 | `set history save [on] [off]`               | Record or don't record the command history into the file specified.                                  |
| 🔵 | `set history size [size]`                   | Set the number of commands gdb keeps in its history list based on the size.                          |
| 🔵 | `set history size unlimited`                | Set the number of commands gdb keeps in its history list as unlimited.                               |
| 🔵 | `set history remove-duplicates [count]`     | Removed the first duplicate entry in history based on count.                                         |
| 🔵 | `set history remove-duplicates unlimited`   | Removed dupicate entrys in history.                                                                  |
| 🔵 | `set history expansion [on] [off]`          | Enable or disable history expansion. History expansion assigns special meaning to the character `!`. |
| 🟢 | `show history`                              | Display all four history states.                                                                     |
| 🔵 | `show history filename`                     | Display the history of filename.                                                                     |
| 🔵 | `show history save`                         | Display the history of save.                                                                         |
| 🔵 | `show history size`                         | Display the history of size.                                                                         |
| 🔵 | `show history exp`                          | Display the history of exp.                                                                          |
| 🟢 | `show commands`                             | Display the last ten commands in the command history.                                                |
| 🔵 | `show commands [n]`                         | Print ten commands centered on command number n.                                                     |
| 🔵 | `show commands +`                           | Print ten commands just after the commands last printed.                                             | 
| 🔵 | `break class::[member]`                     | Set breakpoint on class member. May get menu.                                                        |
| 🔵 | `list class::[member]`                      | List member in class.                                                                                |
| 🔵 | `ptype [class]`                             | Print class members.                                                                                 |
| 🔵 | `print [*this]`      	                     | Print contents of this pointer.                                                                      |
| 🔵 | `rbreak regexpr`     	                     | Useful for breakpoint on overloaded member name.                                                     |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>SHORTCUTS</th><th>SHORTCUTS</th>
<tr><td>

|    | Shortcut   | Command      |   
| :- | :----------| :----------- |
| 🔵 | `b`        | `break`      |
| 🔵 | `c`        | `continue`   |
| 🔵 | `d`        | `delete`     |
| 🔵 | `f`        | `frame`      |
| 🔵 | `i`        | `info`       |
| 🔵 | `j`        | `jump`       |
| 🔵 | `l`        | `list`       |
| 🔵 | `n`        | `next`       |
| 🔵 | `p`        | `print`      |
| 🔵 | `r`        | `run`        |
| 🔵 | `s`        | `step`       |
| 🔵 | `u`        | `until`      |

</td><td>

|    | Shortcut   | Command        |
| :- | :--------- | :------------- |
| 🔵 | `aw`       | `awatch`       |
| 🔵 | `bt`       | `backtrace`    |
| 🔵 | `dir`      | `directory`    |
| 🔵 | `disas`    | `disassemble`  |
| 🔵 | `fin`      | `finish`       |
| 🔵 | `ig`       | `ignore`       |
| 🔵 | `ni`       | `nexti`        |
| 🔵 | `rw`       | `rwatch`       |
| 🔵 | `si`       | `stepi`        |
| 🔵 | `tb`       | `tbreak`       |
| 🔵 | `wa`       | `watch`        |
| 🔵 | `win`      | `winheight`    |
| 🔵 | `ref`      | `refresh`      |
| 🔵 | `disp`     | `display`      |
  
</td></tr>
</table>
</div>

<div>
<table>
<tr><th>MACHINE-LEVEL DEBUG</th>
<tr><td>

|    | Command                  | Result                                          |
| :- | :----------------------- | :---------------------------------------------- |
| 🟢 | `info registers`        	| Print registers sans floats.                    |
| 🔵 | `print/x [$pc]`          | Print one register.                             |



</td></tr>
</table>
</div>

#Your Program’s Input and Output
| 🟢 | `info terminal` | Displays information recorded by gdb about the terminal modes your program is using.
| 🟢 | `run > outfile` | Starts your program, diverting its output to the file outfile.
| 🟢 | `tty /dev/ttyb` | Directs that processes started with subsequent run commands default to do input and output on the terminal /dev/ttyb and have that as their controlling terminal.
| 🟢 | `set inferior-tty [ tty ]` | Set the tty for the program being debugged to tty.
| 🟢 | `show inferior-tty` | Show the current tty for the program being debugged.

#debugging an Already-running Process
| 🟢 | `attach process-id` | This command attaches to a running process—one that was started outside gdb. 
| 🟢 | `set exec-file-mismatch ask|warn|off` | Whether to detect mismatch between the current executable file loaded by gdb and the executable file used to start the process.
| 🟢 | `show exec-file-mismatch` | Show the current value of exec-file-mismatch.
| 🟢 | `detach` | Release the attached process from gdb control. 

#Killing the Child Process
| 🟢 | `kill` | Kill the child process in which your program is running under gdb.

#Debugging Multiple Inferiors Connections and Program
| 🟢 | `info inferiors` | Print a list of all inferiors currently being managed by gdb. 
| 🟢 | `inferior` | Shows information about the current inferior.
| 🟢 | `info connections` | Print a list of all open target connections currently being managed by gdb. 
| 🟢 | `inferior infno`   | Make inferior number infno the current inferior. 
| 🟢 | `add-inferior [ -copies n ] [ -exec executable ] [-no-connection ]` | Adds n inferiors to be run using executable as the executable; n defaults to 1.

| 🟢 | `clone-inferior [ -copies n ] [ infno ]` | Adds n inferiors ready to execute the same program as inferior infno; n defaults to 1, and infno defaults to the number of the current inferior. 
| 🟢 | `remove-inferiors infno...` | Removes the inferior or inferiors infno . . . . It is not possible to remove an
inferior that is running with this command. For those, use the kill or detach
command first.
| 🟢 | `detach inferior infno...` | Detach from the inferior or inferiors identified by gdb inferior number(s) infno.
| 🟢 | `kill inferiors infno...` | Kill the inferior or inferiors identified by gdb inferior number(s) infno . 
| 🟢 | `set print inferior-events [on]` or `[off]` | The set print inferior-events command allows you to enable or disable
printing of messages when gdb notices that new inferiors have started or that
inferiors have exited or have been detached.
| 🟢 | `show print inferior-events` | Show whether messages will be printed when gdb detects that inferiors have
started, exited or have been detached.
| 🟢 | `maint info program-spaces` | Print a list of all program spaces currently being managed by gdb.

<div>
<table>
<tr><th>MULTIPLE THREADS</th>
<tr><td>

|    | Command                                                              | Result                                             |
| :- | :------------------------------------------------------------------- | :------------------------------------------------- |
| 🔵 | ‘thread thread-id’                                                   | Switch among threads.                              |
| 🔵 | ‘info threads’                                                       | Inquire about existing threads.                    |
| 🔵 | `info threads [-gid] [thread-id-list]`                               | Display information about one or more threads.     |
| 🔵 | `thread apply [thread-id-list | all] args`                           | Apply a command to a list of threads.              |
| 🔵 | `maint info sol-threads`                                             | Display info on Solaris user threads.              |
| 🔵 | `thread thread-id`                                                   | Make thread ID thread-id the current thread.       |
| 🔵 | `thread apply [thread-id-list | all [-ascending]] [flag]... command` | Apply the named command to one or more threads.    |
| 🔵 | `[-c]` causes any errors in command to be displayed, and the execution of thread apply then continues.
| 🔵 | `[-s]` causes any errors or empty output produced by a command to be silently ignored.
| 🔵 | `[-q]` Disables printing the thread information.
| 🔵 | `thread apply all -ascending command.`                               | Apply a command to all threads in ascending order. |
| 🔵 | `taas [option]... command`                   | Applies command on all threads, ignoring errors and empty output. |
| 🔵 | `tfaas [option]... command`                  | Applies command on all frames of all threads, ignoring errors and empty output. |
| 🔵 | `thread name [name]`                         | Assign a name to the current thread. |
| 🔵 | `thread find [regexp]`                       | Search for and display thread ids whose name or systag matches the supplied regular expression. |
| 🔵 | `set print thread-events [on]` or `[off]`    | Print messages when gdb notices that new threads have started or that threads have exited. |
| 🔵 | `show print thread-events`                   | Show whether messages will be printed when gdb detects that threads have started and exited. |
| 🔵 | `set libthread-db-search-path [path]`        | Path is a colon-separated list of directories gdb will use to search for libthread_db. |
| 🔵 | `show libthread-db-search-path`              | Display current libthread db search path. |
| 🔵 | `set debug libthread-db [1]` or `[0]`        | |
| 🔵 | `show debug libthread-db`                    | Display of libthread_db-related events. |
| 🔵 | `set debug threads [on]` or `[off]`          | |
| 🔵 | `show debug threads`                         | Print additional messages when threads are created and deleted. |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>FORKS</th>
<tr><td>

|    | Command                                      | Result                                                                               |
| :- | :------------------------------------------- | :----------------------------------------------------------------------------------- |
| 🔵 | `set follow-fork-mode.`                      | Follow the child process instead of the parent process.                              |
| 🔵 | `set follow-fork-mode [parent]` or `[child]` | Set the debugger response to a program call of fork or vfork.                        |
| 🔵 | `show follow-fork-mode`                      | Display the current debugger response to a fork or vfork call.                       |
| 🔵 | `set detach-on-fork.`                        | Debug both the parent and child processes.                                           |
| 🔵 | `set detach-on-fork [on]` or `[off]`         | Detach one of the processes after a fork, or retain debugger control over them both. |
| 🔵 | `show detach-on-fork [on]` or `[off]`        | Show whether detach-on-fork mode is on/off.                                          |
| 🔵 | `set follow-exec-mode [mode]`                | Set debugger response to a program call of exec.                                     |
| 🔵 | `[new]`                                      | Creates a new inferior and rebinds the process to this new inferior.                 |
| 🔵 | `[same]`                                     | Keeps the process bound to the same inferior.                                        |

</td></tr>
</table>
</div>
