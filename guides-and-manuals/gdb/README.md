# GDB Cheat Sheet

<p align="center">
	<a href="#about">About</a> •
	<a href="#references">References</a> •
	<a href="#commands">Commands</a>
</p>

## ABOUT
Welcome to the GDB Debugger Cheat Sheet repository! My goal is to provide a comprehensive list of optimized GDB commands and their descriptions. This repository serves as a concise quick reference guide for developers and enthusiasts working with GDB.

I hope you find this optimized cheat sheet helpful for your GDB debugging needs. Happy debugging!

## REFERENCES
- [100 GDB Tips](https://github.com/hellogcc/100-gdb-tips)
- [GDB Dashboard](https://github.com/cyrus-and/gdb-dashboard)
- [PDF GDB Cheetsheat](https://raw.githubusercontent.com/hellogcc/100-gdb-tips/master/refcard.pdf)
- [GitHub GDB Cheetsheat](https://gist.github.com/rkubik/b96c23bd8ed58333de37f2b8cd052c30)

## COMMANDS

<p align="center">
	<a href="#defination">Definition</a> •
	<a href="#running-the-program">Running the program</a> •
	<a href="#help">Help</a> •
	<a href="#layout">Layout</a> •
	<a href="#breakpoints-and-watchpoints">Breakpoints and watchpoints</a> •
	<a href="#stack-backtrace">Stack backtrace</a> •
	<a href="#browsing-source">Browsing source</a> •
	<a href="#object-file-manipulation">Object file manipulation</a> •
	<a href="#signal-control">Signal control</a> •
	<a href="#machine--level-debug">Machine-level debug</a> •
	<a href="#history-display">History display</a> •
	<a href="#input-and-output">Input and output</a> •
	<a href="#multiple-inferiors-connections">Multiple inferiors connections</a> •
	<a href="#multiple-threads">Multiple threads</a> •
	<a href="#forks">Forks</a> •
	<a href="#shortcuts">Shortcuts</a> •
	<a href="#keyboard-shortcuts">Keyboard shortcuts</a> •
	<a href="#single-key-mode">Single key mode</a> •
</p>

#### DEFINITION
|    |                           |
| :- | :------------------------ |
| 🟢 | Most used commands by me  |
| 🔵 | Least used commands by me |

#### RUNNING THE PROGRAM
<div>
<table>
<tr><th></th>
<tr><td>
  
|    | Command                               | Result                                             |
| :- | :------------------------------------ | :------------------------------------------------- |
| 🟢 | `gdb`        		                     | Start gdb.                                         |
| 🟢 | `gdb --tui [object]`                  | Start gdb with graphic interface.                  |
| 🔵 | `gdb -silent`                         | Start gdb without the beginning information.       |
| 🟢 | `gdb -statistics`                     | Print statistics about time and memory usage.      |
| 🟢 | `gdb [object]`      	                 | Normal debug.                                      |
| 🔵 | `gdb [object] [core]` 	               | core debug (must specify core file).               |
| 🟢 | `gdb [object] [pid]`  	               | Attach to a running process.                       |
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
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### HELP
<div>
<table>
<tr><th></th>
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
| ⚪ | <a href="#commands">↥ Back To Top</a>   | Scroll back top (index).                               |

</td></tr>
</table>
</div>  

#### LAYOUT
<div>
<table>
<tr><th></th>
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
| 🔵 | `refresh`                               | Refresh the screen. This is similar to typing `CTRL` + `L` or `ref`.                    |
| 🔵 | `tui reg float`                         | Show the floating point registers in the register window.                               |
| 🔵 | `tui reg general`                       | Show the general registers in the register window.                                      |
| 🔵 | `tui reg system`                        | Show the system registers in the register window.                                       |
| 🔵 | `tui reg next`                          | Show the next register group. List register groups as well as their order.              |
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
| 🔵 | `set pagination [on/off]`               | Turn the output pagination on or off. Turning pagination off = `set height 0`           |
| 🔵 | `show pagination`                       | Show the current pagination mode.                                                       |
| 🔵 | `set tui border-kind [kind]`            | Select the border appearance for the source, assembly and register windows.             |
| 🔵 | `[space]`                               | Use a space character to draw the border.                                               |
| 🔵 | `[ascii]`                               | Use ascii characters `+`, `-` and `|` to draw the border.                               |
| 🔵 | `[acs]`                                 | Use the Alternate Character Set to draw the border.                                     |
| 🔵 | `[drawn]`                               | Using character line graphics if the terminal supports them.                            |
| 🔵 | `set tui border-mode [mode]`            | Select the display attributes for the inactive window border.                           |
| 🔵 | `set tui active-border-mode [mode]`     | Select the display attributes for the active window border.                             |
| 🔵 | `[standout]`                            | Use standout mode.                                                                      |
| 🔵 | `[reverse]`                             | Use reverse video mode.                                                                 |
| 🔵 | `[half]`                                | Use half bright mode.                                                                   |
| 🔵 | `[half-standout]`                       | Use half bright and standout mode.                                                      |
| 🔵 | `[bold]`                                | Use extra bright or bold mode.                                                          |
| 🔵 | `[bold-standout]`                       | Use extra bright or bold and standout mode.                                             |
| ⚪ | <a href="#commands">↥ Back To Top</a>   | Scroll back top (index).                                                                |

</td></tr>
</table>
</div>

#### BREAKPOINTS AND WATCHPOINTS
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                                                      | Result                                                      |
| :--| ------------------------------------------------------------ | ----------------------------------------------------------- |
| 🟢 | `break [line/function]`                                      | Set a breakpoint on a line or function.                     |
| 🔵 | `break main.c:42`                                            | Set breakpoint at the file and (line or function).          |
| 🔵 | `tbreak [line/function]`                                     | Set a temporary breakpoint.                                 |
| 🟢 | `watch [variable]`                                           | Set a software watchpoint on a variable.                    |
| 🟢 | `info breakpoints`                                           | Show breakpoints and watchpoints.                           |
| 🔵 | `info watchpoints`                                           | Show current watchpoints.                                   |
| 🟢 | `delete [breakpoint/watchpoint number]`                      | Delete a breakpoint or watchpoint by number.                |
| 🟢 | `delete`                                                     | Delete all breakpoints and watchpoints (prompted).          |
| 🟢 | `clear`                                                      | Delete breakpoints and watchpoints at the current line.     |
| 🟢 | `clear [line/function]`                                      | Delete breakpoints or watchpoints at a line or function.    |
| 🟢 | `disable [breakpoint/watchpoint number]`                     | Turn a breakpoint or watchpoint off, but don't remove it.   |
| 🟢 | `enable [breakpoint/watchpoint number]`                      | Turn a disabled breakpoint or watchpoint back on.           |
| 🔵 | `commands [breakpoint/watchpoint number] [commands] end`     | Set GDB commands with a breakpoint or watchpoint.           |
| 🔵 | `ignore [breakpoint/watchpoint number] [n times]`            | Ignore a breakpoint or watchpoint n times before activation.|
| 🔵 | `condition [breakpoint/watchpoint number] [expression]`      | End only if the expression is true.                         |
| 🔵 | `condition [breakpoint/watchpoint number] [condition]`       | End only if the condition is true.                          |
| 🔵 | `condition [breakpoint/watchpoint number]`                   | Delete condition at a breakpoint or watchpoint number.      |
| ⚪ | <a href="#commands">↥ Back To Top</a>                        | Scroll back top (index).                                    |

</td></tr>
</table>
</div>

#### STACK BACKTRACE
<div>
<table>
<tr><th></th>
<tr><td>
  
|    | Command         | Result                                  |
| :- | --------------- | --------------------------------------- |
| 🟢 | `bt`            | Print stack backtrace.                  |
| 🔵 | `frame`         | Show current execution position.        |
| 🔵 | `up`            | Move up stack trace (towards main).     |
| 🔵 | `down`          | Move down stack trace (away from main). |
| 🟢 | `info locals`   | Print automatic variables in frame.     |
| 🟢 | `info args`     | Print function parameters.              |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### BROWSING SOURCE
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                                   | Result                                              |
| :- | :---------------------------------------- | :-------------------------------------------------- |
| 🔵 | `list [20]`                               | List 10 lines around line `20`.                     |
| 🔵 | `list [1,10]`                             | List lines `1` to `10`.                             |
| 🔵 | `list [main]`                             | List lines around function `main`.                  |
| 🔵 | `list [basic.c:main]`                     | List from another file `basic.c`.                   |
| 🔵 | `list -`                                  | List previous 10 lines.                             |
| 🟢 | `info address [Symbol name]`              | Displays the address of a given symbol.             |
| 🔵 | `list [*0x22e4]`                          | List source at address `p0x22e4`.                   |
| 🔵 | `cd [dir]`                                | Change current directory to `dir`.                  |
| 🔵 | `pwd`                                     | Print working directory.                            |
| 🔵 | `search [regular expression]`             | Forward search for regular expression.              |
| 🔵 | `reverse-search [regular expression]`     | Backward search for regular expression.             |
| 🔵 | `dir [dirname]`                           | Add directory `dirname` to source path.             |
| 🔵 | `dir`                                     | Reset source path to nothing.                       |
| 🔵 | `show directories`                        | Show source path.                                   |
| ⚪ | <a href="#commands">↥ Back To Top</a>     | Scroll back top (index).                            |

</td></tr>
</table>
</div>  

#### BROWSING DATA
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                               | Result                                         |
| :- | :------------------------------------ | :--------------------------------------------- |
| 🟢 | `print [expression]`                  | Print variable, added to value history.        |
| 🟢 | `print/x [expression]`                | Print variable in hex format.                  |
| 🔵 | `print [array[i]@count]`              | Artificial array - print array range.          |
| 🔵 | `print $`                             | Print last value.                              |
| 🔵 | `print *$->next`                      | Print thru history list.                       |
| 🔵 | `print $1`                            | Print value 1 from value history.              |
| 🔵 | `print ::gx`                          | Force scope to be global.                      |
| 🔵 | `print [basic.c]::gx`                 | Global scope in named file.                    |
| 🔵 | `print/x [&main]`                     | Print address of function.                     |
| 🔵 | `x/countFormatSize [address]`         | Low-level examine command.                     |
| 🔵 | `x/x [&gx]`                           | Print gx in hex.                               |
| 🔵 | `x/4wx [&main]`                       | Print 4 longs at start of main in hex format.  |
| 🔵 | `x/gf [&gd1]`                         | Print double.                                  |
| 🔵 | `help x`                              | Show formats for x.                            |
| 🟢 | `info locals`                         | Print local automatics only.                   |
| 🟢 | `info functions [regular expression]` | Print function names.                          |
| 🟢 | `info variables [regular expression]` | Print global variable names.                   |
| 🟢 | `ptype [expression]`                  | Print type definition.                         |
| 🟢 | `whatis [expression]`                 | Print type of expression.                      |
| 🟢 | `set [variable] = [expression]`       | Assign value.                                  |
| 🟢 | `display [expression]`                | Display expression result at stop.             |
| 🔵 | `undisplay`                           | Delete displays.                               |
| 🟢 | `info display`                        | Show displays.                                 |
| 🟢 | `show values`                         | Print value history.                           |
| 🟢 | `info history`                        | Print value history.                           |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                       |

</td></tr>
</table>
</div>  

#### OBJECT FILE MANIPULATION
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                  | Result                               |
| :- | :----------------------- | :----------------------------------- |
| 🔵 | `file [object]`      		| load new file for debug (sym+exec)   |
| 🔵 | `file`             		  | discard sym+exec file info           |
| 🔵 | `symbol-file [object]`   | load only symbol table               |
| 🔵 | `exec-file [object]` 		| specify object to run (not sym-file) |
| 🔵 | `core-file [core]`   		| post-mortem debugging                |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### SIGNAL CONTROL
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                  | Result                                     |
| :- | :----------------------- | :----------------------------------------- |
| 🟢 | `info signals`           | Print signal setup.                        |
| 🔵 | `handle signo actions`   | Set debugger actions for signal.           |
| 🔵 | `handle INT print`       | Print message when signal occurs.          |
| 🔵 | `handle INT noprint`     | Don't print message.                       |
| 🔵 | `handle INT stop`        | Stop program when signal occurs.           |
| 🔵 | `handle INT nostop`      | Don't stop program.                        |
| 🔵 | `handle INT pass`        | Allow the program to receive a signal.     |
| 🔵 | `handle INT nopass`      | Debugger catches signal; program doesn't.  |
| 🔵 | `signal signo`           | Continue and send signal to program.       |
| 🔵 | `signal 0`               | Continue and send no signal to the program.|
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### MACHINE-LEVEL DEBUG
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                  | Result                                              |
| :- | :----------------------- | :-------------------------------------------------- |
| 🟢 | `info registers`        	| Print registers sans floats.                        |
| 🟢 | `info all-registers`     | Print all registers.                                |
| 🔵 | `print/x [$pc]`          | Print one register.                                 |
| 🔵 | `stepi`        		      | Single step at machine level.                       |
| 🔵 | `nexti`        		      | Single step (over functions) at the machine level.  |
| 🔵 | `display/i [$pc]`        | Print current instruction in display.               |
| 🔵 | `x/x [&gx]`        	    | Print variable gx in hex.                           |
| 🟢 | `info line [42]`         | Print addresses for object code for line 42.        |
| 🟢 | `info line [*0x2c4e]`    | Print line number of object code at address.        |
| 🔵 | `x/10i [main]`           | Disassemble first 10 instructions in main.          |
| 🔵 | `disassemble [address]`  | Dissassemble code for function around address.      |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### HISTORY DISPLAY
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                                     | Result                                                                       |
| :- | :------------------------------------------ | :--------------------------------------------------------------------------- |
| 🟢 | `show commands`                             | Print command history.                                                       |
| 🔵 | `info editing`       	                     | Print command history.                                                       |
| 🔵 | `set history filename [fname]`              | Set the name of the GDB command history file to fname.                       |
| 🔵 | `set history save`                          | Record command history in a file.                                            |
| 🔵 | `set history save [on/off]`                 | Record or don't record the command history into the file specified.          |
| 🔵 | `set history size [size]`                   | Set the number of commands gdb keeps in its history list based on the size.  |
| 🔵 | `set history size unlimited`                | Set the number of commands gdb keeps in its history list as unlimited.       |
| 🔵 | `set history remove-duplicates [count]`     | Removed the first duplicate entry in history based on the count.                 |
| 🔵 | `set history remove-duplicates unlimited`   | Removed dupicate entrys in history.                                          |
| 🔵 | `set history expansion [on/off]`            | Enable or disable history expansion.                                         |
| 🟢 | `show history`                              | Display all four history states.                                             |
| 🔵 | `show history filename`                     | Display the history of filename.                                             |
| 🔵 | `show history save`                         | Display the history of save.                                                 |
| 🔵 | `show history size`                         | Display the history of size.                                                 |
| 🔵 | `show history exp`                          | Display the history of exp.                                                  |
| 🟢 | `show commands`                             | Display the last ten commands in the command history.                        |
| 🔵 | `show commands [n]`                         | Print ten commands centered on command number n.                             |
| 🔵 | `show commands +`                           | Print ten commands just after the commands last printed.                     | 
| 🔵 | `break class::[member]`                     | Set breakpoint on class member. May get a menu.                                |
| 🔵 | `list class::[member]`                      | List member in class.                                                        |
| 🔵 | `ptype [class]`                             | Print class members.                                                         |
| 🔵 | `print [*this]`      	                     | Print contents of this pointer.                                              |
| 🔵 | `rbreak [regular expression]`               | Useful for breakpoint on overloaded member name.                             |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### INPUT AND OUTPUT
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                                 | Result                                                                     |
| :- | :-------------------------------------- | :------------------------------------------------------------------------- |
| 🔵 | `info terminal`                         | Displays information recorded about the terminal modes.                    |
| 🔵 | `run > outfile`                         | Starts your program, diverting its output to the file outfile.             |
| 🔵 | `tty /dev/ttyb`                         | Default processes to do input and output on the terminal /dev/ttyb.        |
| 🔵 | `set inferior-tty [tty]`                | Set the tty for the program being debugged to tty.                         |
| 🔵 | `show inferior-tty`                     | Show the current tty for the program being debugged.                       |
| 🔵 | `attach process-id`                     | Attach to a running process that was started outside gdb.                  |
| 🔵 | `set exec-file-mismatch [ask]`          | Display a warning and ask the user whether to load the process executable. |
| 🔵 | `set exec-file-mismatch [warn]`         | Just display a warning.                                                    |
| 🔵 | `set exec-file-mismatch [off]`          | Don’t attempt to detect a mismatch.                                        |
| 🔵 | `show exec-file-mismatch`               | Show the current value of exec-file-mismatch.                              |
| 🔵 | `detach`                                | Release the attached process from gdb control.                             |
| 🔵 | `kill`                                  | Kill the child process in which your program is running.                   |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>
  
#### MULTIPLE INFERIRORS CONNECTIONS
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                                      | Result                                                                 |
| :- | :------------------------------------------- | :--------------------------------------------------------------------- |
| 🔵 | `info inferiors`                             | Print a list of all inferiors currently being managed by gdb.          |
| 🔵 | `inferior`                                   | Shows information about the current inferior.                          |
| 🔵 | `info connections`                           | Print a list of all open target connections currently being managed.   | 
| 🔵 | `inferior [id]`                              | Make inferior [id] the current inferior.                               |
| 🔵 | `add-inferior`                               | Adds n inferiors to be run using executable as the executable.         |
| 🔵 | `[-copies n]`                                |                                                                        |
| 🔵 | `[-exec executable]`                         |                                                                        |
| 🔵 | `[-no-connection]`                           |                                                                        |
| 🔵 | `clone-inferior [-copies n] [id]`            | Adds n inferiors ready to execute the same program as inferior [id].   |
| 🔵 | `remove-inferiors [id]`                      | Removes the inferior or inferiors.                                     |
| 🔵 | `detach inferior [id]`                       | Detach from the inferior(s) identified by inferior [id].               |
| 🔵 | `kill inferiors [id]`                        | Kill the inferior or inferiors identified by inferior [id].            |
| 🔵 | `set print inferior-events [on/off]`         | Enable or disable printing of new inferiors.                           |
| 🔵 | `show print inferior-events`                 | Print if inferiors have started, exited or have been detached.         |
| 🔵 | `maint info program-spaces`                  | Print a list of all program spaces currently being managed.            |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### MULTIPLE THREADS
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                                      | Result                                                                           |
| :- | :------------------------------------------- | :------------------------------------------------------------------------------- |
| 🔵 | `thread thread-id`                           | Switch among threads.                                                            |
| 🔵 | `info threads`                               | Inquire about existing threads.                                                  |
| 🔵 | `info threads [-gid] [thread-id-list]`       | Display information about one or more threads.                                   |
| 🔵 | `thread apply [thread-id-list] args`         | Apply a command to a list of threads.                                            |
| 🔵 | `maint info sol-threads`                     | Display info on Solaris user threads.                                            |
| 🔵 | `thread thread-id`                           | Make thread ID thread-id the current thread.                                     |
| 🔵 | `thread apply [thread-id-list] command`      | Apply the named command to one or more threads.                                  |
| 🔵 | `[-c]`                                       | Display errors and the execution of the thread apply then continues.             |
| 🔵 | `[-s]`                                       | Errors or empty output produced by a command to be silently ignored.             |
| 🔵 | `[-q]`                                       | Disables printing the thread information.                                        |
| 🔵 | `thread apply all -ascending command.`       | Apply a command to all threads in ascending order.                               |
| 🔵 | `taas [option]... command`                   | Applies command on all threads, ignoring errors and empty output.                |
| 🔵 | `tfaas [option]... command`                  | Applies command on all frames of all threads, ignoring errors and empty output.  |
| 🔵 | `thread name [name]`                         | Assign a name to the current thread.                                             |
| 🔵 | `thread find [regexp]`                       | Search for and display thread ids whose name or systag matches.                  |
| 🔵 | `set print thread-events [on/off]`           | Print messages when new threads have started or exited.                          |
| 🔵 | `show print thread-events`                   | Show whether messages will be printed when threads have started and exited.      |
| 🔵 | `set libthread-db-search-path [path]`        | List of directories gdb will use to search for libthread_db.                     |
| 🔵 | `show libthread-db-search-path`              | Display current libthread db search path.                                        |
| 🔵 | `set debug libthread-db [1/0]`               | Set the debug libthread-db as on or off.                                         |
| 🔵 | `show debug libthread-db`                    | Display of libthread_db-related events.                                          |
| 🔵 | `set debug threads [on/off]`                 | Set the debug threads as on or off.                                              |
| 🔵 | `show debug threads`                         | Print additional messages when threads are created and deleted.                  |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### FORKS
<div>
<table>
<tr><th></th>
<tr><td>

|    | Command                                      | Result                                                                               |
| :- | :------------------------------------------- | :----------------------------------------------------------------------------------- |
| 🔵 | `set follow-fork-mode.`                      | Follow the child process instead of the parent process.                              |
| 🔵 | `set follow-fork-mode [parent]`              | Set the debugger response to a program call of fork.                                 |
| 🔵 | `set follow-fork-mode [child]`               | Set the debugger response to a program call of vfork.                                |
| 🔵 | `show follow-fork-mode`                      | Display the current debugger response to a fork or vfork call.                       |
| 🔵 | `set detach-on-fork.`                        | Debug both the parent and child processes.                                           |
| 🔵 | `set detach-on-fork [on/off]`                | Detach one of the processes after a fork, or retain debugger control over them both. |
| 🔵 | `show detach-on-fork [on/off]`               | Show whether detach-on-fork mode is on/off.                                          |
| 🔵 | `set follow-exec-mode [mode]`                | Set debugger response to a program call of exec.                                     |
| 🔵 | `[new]`                                      | Creates a new inferior and rebinds the process to this new inferior.                 |
| 🔵 | `[same]`                                     | Keeps the process bound to the same inferior.                                        |
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### SHORTCUTS
<div>
<table>
<tr><th></th><th></th>
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
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

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
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### KEYBOARD SHORTCUTS
<div>
<table>
<tr><th></th>
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
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>

#### SINGLE KEY MODE
<div>
<table>
<tr><th></th>
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
| ⚪ | <a href="#commands">↥ Back To Top</a> | Scroll back top (index).                           |

</td></tr>
</table>
</div>
