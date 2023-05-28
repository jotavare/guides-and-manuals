set follow-fork-mode <child or parent>
set height lpp
set height unlimited
show height
set width cpl
set width unlimited
show width
set pagination on
set pagination off
show pagination

set history filename fname 
set history save
set history save on
history filename command
set history save off
set history size size
History expansion
!
!=
set history expansion on
set history expansion
Enable history expansion..
set history expansion off
Disable history expansion.
show history
show history filename
show history save
show history size
show history expansion
show commands
show commands n
show commands +
  
gdb program
gdb program core
gdb program 1234
would attach gdb to process 1234
gdb --args gcc -O2 -c foo.c
gdb -silent

gdb -statistics
gdbtui gdb --tui 

$ gdb -q -tui <file>

Then when in gdb:

(gdb) break main
(gdb) run
(gdb) layout asm
(gdb) layout reg
(gdb) list 10 
winheight src +4
winheight cmd
win win_name src cmd asm regs src
layout asm
layout split
layout regs
tui reg float
tui reg system
tui reg general
layout next
layout prev
layout src
(gdb) shell ls
(gdb) !ls
-tui” parameters (for example: gdb -tui program), or use " Crtl+X+A

# GDB Commands

- [100 GDB Tips](https://github.com/hellogcc/100-gdb-tips)
- [GDB Dashboard](https://github.com/cyrus-and/gdb-dashboard)
- [GDB Cheetsheat](https://raw.githubusercontent.com/hellogcc/100-gdb-tips/master/refcard.pdf)
- [GDB Cheetsheat](https://gist.github.com/rkubik/b96c23bd8ed58333de37f2b8cd052c30)

<div>
<table>
<tr><th>Running the Program</th>
<tr><td>

|    | Command                               | Result                                             |
| :- | :------------------------------------ | :------------------------------------------------- |
| 🔵 | `gdb` <program> [core dump]           | Start GDB (with optional core dump).               |
| 🔵 | `gdb --args` [program] [args...]      | Start GDB and pass arguments.                      |
| 🟢 | `gdb` --pid` [pid]                    | Start GDB and attach to process.                   |
| 🟢 | `run`                                 | Run the program with current arguments.            |
| 🔵 | `run` [args] [redirection]            | Run with args and redirection.                     |
| 🟢 | `set args` [args...]                  | Set arguments for run.                             |
| 🟢 | `show args`                           | Show current arguments to run.                     |
| 🔵 | `cont`                                | Continue the program.                              |
| 🟢 | `step`                                | Single step the program, also step into functions. |
| 🟢 | `step` [number of lines]              | Step n number of lines.                            |
| 🟢 | `next`                                | Next line.                                         |
| 🟢 | `next` [number of lines]              | Next n number of lines.                            |
| 🔵 | `attach` [process-id]                 | Attach to running program.                         |
| 🔵 | `detach`                              | Detach from running program.                       |
| 🟢 | `finish`                              | Finish current function's execution.               |
| 🟢 | `kill`                                | Kill current executing program.                    |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>Help</th>
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
<tr><th>Keyboard Shortcuts</th>
<tr><td>
  
|    | Shortcut            | Result                                                   |
| -- | ------------------- | -------------------------------------------------------- |
| 🟢 | `CTRL` + `C`        | Actually SIGINT, stop execution of current program.      |
| 🟢 | `CTRL` + `A`        | Enter or leave the TUI mode.                             |
| 🟢 | `CTRL` + `X` + `1`  | Use a TUI layout with only one window.                   |
| 🟢 | `CTRL` + `X` + `2`  | Use a TUI layout with at least two windows.              |
| 🟢 | `CTRL` + `O`        | Change the active window (use scrolling and arrow keys). |
| 🔵 | `PgUp Scroll`       | The active window one page up.                           |
| 🔵 | `PgDn Scroll`       | The active window one page down.                         |
| 🔵 | `Up Scroll`         | The active window one line up.                           |
| 🔵 | `Down Scroll`       | The active window one line down.                         |
| 🔵 | `Left Scroll`       | The active window one column left.                       |
| 🔵 | `Right Scroll`      | The active window one column right.                      |
| 🟢 | `CTRL` + `L`        | Refresh the screen.                                      |
| 🟢 | `CTRL` + `P`        | Previous command.                                        |
| 🟢 | `CTRL` + `N`        | Next command.                                            |
| 🟢 | `CTRL` + `B`        | Move left in the command text.                           |
| 🟢 | `CTRL` + `F`        | Move right in the command text.                          |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>Breakpoints and Watchpoints</th>
<tr><td>

|    | Command                                                      | Result                                                      |
| :--| ------------------------------------------------------------ | ----------------------------------------------------------- |
| 🟢 | `break` [line or function]                                   | Set a breakpoint on a line or function.                     |
| 🔵 | `break` main.c:42                                            | Set breakpoint at file and (line or function).              |
| 🔵 | `tbreak` [line or function]                                  | Set a temporary breakpoint.                                 |
| 🟢 | `watch` [variable]                                           | Set a software watchpoint on a variable.                    |
| 🟢 | `info breakpoints`                                           | Show breakpoints and watchpoints.                           |
| 🔵 | `info watchpoints`                                           | Show current watchpoints.                                   |
| 🔵 | `delete` [breakpoint or watchpoint number]                   | Delete a breakpoint or watchpoint by number.                |
| 🔵 | `delete`                                                     | Delete all breakpoints and watchpoints (prompted).          |
| 🟢 | `clear`                                                      | Delete breakpoints and watchpoints at the current line.     |
| 🔵 | `clear` [line or function]                                   | Delete breakpoints or watchpoints at a line or function.    |
| 🔵 | `disable` [breakpoint or watchpoint number]                  | Turn a breakpoint or watchpoint off, but don't remove it.   |
| 🔵 | `enable` [breakpoint or watchpoint number]                   | Turn a disabled breakpoint or watchpoint back on.           |
| 🔵 | `commands` [breakpoint or watchpoint number] [commands] `end`| Set GDB commands with a breakpoint or watchpoint.           |
| 🔵 | `ignore` [breakpoint or watchpoint number] [n times]         | Ignore a breakpoint or watchpoint n times before activation.|
| 🔵 | `condition` [breakpoint or watchpoint number] [expression]   | End only if the expression is true.                         |
| 🔵 | `condition` [breakpoint or watchpoint number] [condition]    | End only if the condition is true.                          |
| 🔵 | `condition` [breakpoint or watchpoint number]                | Delete condition at a breakpoint or watchpoint number.      |
  
</td></tr>
</table>
</div>
  
<div>
<table>
<tr><th>Stack Backtrace</th>
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
<tr><th>Browsing Source</th>
<tr><td>

|    | Command                      | Result                                              |
| :- | :--------------------------- | :-------------------------------------------------- |
| 🔵 | `list` [20]                  | List 10 lines around line `20`.                     |
| 🔵 | `list` [1,10]                | List lines `1` to `10`.                             |
| 🔵 | `list` [main]                | List lines around function `main`.                  |
| 🔵 | `list` [basic.c:main]        | List from another file `basic.c`.                   |
| 🔵 | `list -`                     | List previous 10 lines.                             |
| 🔵 | `info address` [Symbol name] | Displays the address of a given symbol.             |
| 🔵 | `list` [*0x22e4]             | List source at address `p0x22e4`.                   |
| 🔵 | `cd` [dir]                   | Change current directory to `dir`.                  |
| 🔵 | `pwd`                        | Print working directory.                            |
| 🔵 | `search regexpr`             | Forward search for regular expression `regexpr`.    |
| 🔵 | `reverse-search regexpr`     | Backward search for regular expression `regexpr`.   |
| 🔵 | `dir` [dirname]              | Add directory `dirname` to source path.             |
| 🔵 | `dir`                        | Reset source path to nothing.                       |
| 🔵 | `show directories`           | Show source path.                                   |

</td></tr>
</table>
</div>  

<div>
<table>
<tr><th>Browsing Data</th>
<tr><td>

|    | Command                         | Result |
| :- | :------------------------------ | :----- |
| 🟢 | `print` [expression]            | Print variable, added to value history. |
| 🟢 | `print/x` [expression]          | Print variable in hex format. |
| 🔵 | `print` [array[i]@count]        | Artificial array - print array range. |
| 🔵 | `print $`        	             | Print last value. |
| 🔵 | `print *$->next`                | Print thru history list. |
| 🔵 | `print $1`        	             | Print value 1 from value history. |
| 🔵 | `print ::gx`                    | Force scope to be global. |
| 🔵 | `print [basic.c]::gx`           | Global scope in named file. |
| 🔵 | `print/x` [&main]               | Print address of function. |
| 🔵 | `x/countFormatSize` [address]   | Low-level examine command. |
| 🔵 | `x/x` [&gx]        	           | Print gx in hex. |
| 🔵 | `x/4wx` [&main]                 | Print 4 longs at start of main in hex format. |
| 🔵 | `x/gf` [&gd1]                   | Print double. |
| 🔵 | `help x`        	               | Show formats for x. |
| 🟢 | `info locals`                   | Print local automatics only. |
| 🔵 | `info functions regexp`         | Print function names. |
| 🔵 | `info variables regexp`         | Print global variable names. |
| 🟢 | `ptype` [expression]            | Print type definition. |
| 🟢 | `whatis` [expression]           | Print type of expression. |
| 🟢 | `set` [variable] = [expression] | Assign value. |
| 🔵 | `display` [expression]          | Display expression result at stop. |
| 🔵 | `undisplay`                     | Delete displays. |
| 🔵 | `info display`                  | Show displays. |
| 🔵 | `show values`                   | Print value history. |
| 🔵 | `info history`                  | Print value history. |

</td></tr>
</table>
</div>  

<div>
<table>
<tr><th>Object File manipulation</th>
<tr><td>

|    | Command                  | Result                               |
| :- | :----------------------- | :----------------------------------- |
| 🔵 | `file` [object]      		| load new file for debug (sym+exec)   |
| 🔵 | `file`             		  | discard sym+exec file info           |
| 🔵 | `symbol-file` [object]   | load only symbol table               |
| 🔵 | `exec-file` [object] 		| specify object to run (not sym-file) |
| 🔵 | `core-file` [core]   		| post-mortem debugging                |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>Signal Control</th>
<tr><td>

|    | Command                  | Result                                    |
| :- | :----------------------- | :---------------------------------------- |
| 🔵 | `info signals`        	  | Print signal setup.                       |
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
<tr><th>Machine-level Debug</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| info registers        	  | print registers sans floats |
| info all-registers        | print all registers |
| print/x $pc             	| print one register |
| stepi        		          | single step at machine level |
| si        		            | single step at machine level |
| nexti        		          | single step (over functions) at machine level |
| ni        		            | single step (over functions) at machine level |
| display/i $pc        	    | print current instruction in display |
| x/x &gx        	        	| print variable gx in hex |
| info line 22            	| print addresses for object code for line 22 |
| info line *0x2c4e         | print line number of object code at address |
| x/10i main              	| disassemble first 10 instructions in \fImain\fR |
| disassemble addr          | dissassemble code for function around addr |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>History Display</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| show commands                  | print command history (>= gdb 4.0) |
| info editing       	           | print command history (gdb 3.5) |
| ESC-CTRL-J        	           | switch to vi edit mode from emacs edit mode |
| set history expansion on       | turn on c-shell like history |
| break class::member            | set breakpoint on class member. may get menu |
| list class::member             | list member in class |
| ptype class                    | print class members |
| print *this        	           | print contents of this pointer |
| rbreak regexpr     	           | useful for breakpoint on overloaded member name |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>Miscellaneous</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| define command ... end      | define user command |
| RETURN                      | repeat last command |
| shell command args          | execute shell command |
| source file                 | load gdb commands from file |
| quit                        | quit gdb |

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>Shortcuts</th><th>Shortcuts</th>
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
