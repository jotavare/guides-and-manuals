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

246 Debugging with gdb
To issue a command to gdb without affecting certain aspects of the state which is seen
by users, prefix it with ‘server ’ (see Section 28.2 [Server Prefix], page 356). This means
that this command will not affect the command history, nor will it affect gdb’s notion of
which command to repeat if RET is pressed on a line by itself.
The server prefix does not affect the recording of values into the value history; to print
a value without recording it into the value history, use the output command instead of the
print command.
Here is the description of gdb commands related to command history.
set history filename fname
Set the name of the gdb command history file to fname. This is the file where
gdb reads an initial command history list, and where it writes the command
history from this session when it exits. You can access this list through history
expansion or through the history command editing characters listed below.
This file defaults to the value of the environment variable GDBHISTFILE, or to
‘./.gdb_history’ (‘./_gdb_history’ on MS-DOS) if this variable is not set.
set history save
set history save on
Record command history in a file, whose name may be specified with the set
history filename command. By default, this option is disabled.
set history save off
Stop recording command history in a file.
set history size size
Set the number of commands which gdb keeps in its history list. This defaults
to the value of the environment variable HISTSIZE, or to 256 if this variable is
not set.
History expansion assigns special meaning to the character !. See Section 32.1.1 [Event
Designators], page 385, for more details.
Since ! is also the logical not operator in C, history expansion is off by default. If you
decide to enable history expansion with the set history expansion on command, you may
sometimes need to follow ! (when it is used as logical not, in an expression) with a space
or a tab to prevent it from being expanded. The readline history facilities do not attempt
substitution on the strings != and !(, even when history expansion is enabled.
The commands to control history expansion are:
set history expansion on
set history expansion
Enable history expansion. History expansion is off by default.
set history expansion off
Disable history expansion.
Chapter 22: Controlling gdb 247
show history
show history filename
show history save
show history size
show history expansion
These commands display the state of the gdb history parameters. show
history by itself displays all four states.
show commands
Display the last ten commands in the command history.
show commands n
Print ten commands centered on command number n.
show commands +
Print ten commands just after the commands last printed
  
  
gdb program
You can also start with both an executable program and a core file specified:
gdb program core
You can, instead, specify a process ID as a second argument, if you want to debug a
running process:
gdb program 1234
would attach gdb to process 1234 (unless you also have a file named ‘1234’; gdb does check
for a core file first).
Taking advantage of the second command-line argument requires a fairly complete op-
erating system; when you use gdb as a remote debugger attached to a bare board, there
may not be any notion of “process”, and there is often no way to get a core dump. gdb
will warn you if it is unable to attach or to read core dumps.
You can optionally have gdb pass any arguments after the executable file to the inferior
using --args. This option stops option processing.
gdb --args gcc -O2 -c foo.c
This will cause gdb to debug gcc, and to set gcc’s command-line arguments (see
Section 4.3 [Arguments], page 28) to ‘-O2 -c foo.c’.
You can run gdb without printing the front material, which describes gdb’s
non-warranty, by specifying -silent:
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

b -> break
c -> continue
d -> delete
f -> frame
i -> info
j -> jump
l -> list
n -> next
p -> print
r -> run
s -> step
u -> until

There are also two or more letters, such as:

aw -> awatch
bt -> backtrace
dir -> directory
disas -> disassemble
fin -> finish
ig -> ignore
ni -> nexti
rw -> rwatch
si -> stepi
tb -> tbreak
wa -> watch
win -> winheight

  (gdb) shell ls

or

(gdb) !ls


-tui” parameters (for example: gdb -tui program), or use " Crtl+X+A
# GDB Commands

- [100 GDB Tips](https://github.com/hellogcc/100-gdb-tips)
- [GDB Dashboard](https://github.com/cyrus-and/gdb-dashboard)
- [GDB Cheetsheat](https://raw.githubusercontent.com/hellogcc/100-gdb-tips/master/refcard.pdf)

<div>
<table>
<tr><th>RUN</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| `gdb` <program> [core dump]           | Start GDB (with optional core dump). |
| `gdb` --args <program> <args...>      | Start GDB and pass arguments |
| `gdb` --pid <pid>                     | Start GDB and attach to process. |
| `run`                                 | run the program with current arguments |
| run args redirection                  | run with args and redirection |
| `set args` <args...>                  | set arguments for run |
| show args                             | show current arguments to run |
| cont                                  | continue the program |
| step                                 | single step the program; step into functions |
| step count                            | singlestep \fIcount\fR times |
| next                                  | step but step over functions |
| next count                            | next \fIcount\fR times |
| CTRL-C                                | actually SIGINT, stop execution of current program |
| attach process-id                     | attach to running program |
| detach                                | detach from running program |
| finish                                | finish current function's execution |
| `kill`                                | kill current executing program |

</td></tr>
</table>
</div>
  
<div>
<table>
<tr><th>HELP</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| `help` or `-h` 	                        | list command classes |
| `help running`                          | list commands in one command class |
| `help run`        	                    | bottom-level help for a command "run" | 
| `help info`                             | list info commands (running program state) |
| `help info line`                        | help for a particular info comman |
| `help show`                             | list show commands (gdb state) |
| `help show commands`                    | specific help for a show comma |

</td></tr>
</table>
</div>
  
<div>
<table>
<tr><th>Breakpoints and Watchpoints</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| `break` [line or function]                                    | Set a breakpoint on a line or function.                       |
| `break` main.c:42                                             | Set breakpoint at file and (line or function).                |
| `tbreak` [line or function]                                   | Set a temporary breakpoint.                                   |
| `watch` [variable]                                            | Set a software watchpoint on a variable.                      |
| `info breakpoints`                                            | Show breakpoints and watchpoints.                             |
| `info watchpoints`                                            | Show current watchpoints.                                     |
| `delete` [breakpoint or watchpoint number]                    | Delete a breakpoint or watchpoint by number.                  |
| `delete`                                                      | Delete all breakpoints and watchpoints (prompted).            |
| `clear`                                                       | Delete breakpoints and watchpoints at the current line.       |
| `clear` [line or function]                                    | Delete breakpoints or watchpoints at a line or function.      |
| `disable` [breakpoint or watchpoint number]                   | Turn a breakpoint or watchpoint off, but don't remove it.     |
| `enable` [breakpoint or watchpoint number]                    | Turn a disabled breakpoint or watchpoint back on.             |
| `commands` [breakpoint or watchpoint number] [commands] `end` | Set GDB commands with a breakpoint or watchpoint.             |
| `ignore` [breakpoint or watchpoint number] [n times]          | Ignore a breakpoint or watchpoint n times before activation.  |
| `condition` [breakpoint or watchpoint number] [expression]    | End only if the expression is true. `condition 1 i == TRUE`.  |
| `condition` [breakpoint or watchpoint number] [condition]     | End only if the condition is true. `condition 1 i == 2`.      |
| `condition` [breakpoint or watchpoint number]                 | Delete condition at a breakpoint or watchpoint number.        |
  
</td></tr>
</table>
</div>
  
<div>
<table>
<tr><th>STACK BACKTRACE</th>
<tr><td>
  
| Color | Command | Result |
| :------ | :------ | :----- |
| 🟢 | `bt`                  | print stack backtrace |
| 🔵 | `frame`        	      | show current execution position |
| 🔵 | `up`        	        | move up stack trace  (towards main) |
| 🔵 | `down`        	      | move down stack trace (away from main) |
| 🟢 | `info locals`         | print automatic variables in frame |
| 🟢 | `info args`           | print function parameters | 

</td></tr>
</table>
</div>
  
<div>
<table>
<tr><th>BROWSING SOURCE</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| list 101                  | list 10 lines around line 101 |
| list 1,10                 | list lines 1 to 10 |
| list main  	              | list lines around function |
| list basic.c:main         | list from another file basic.c |
| list -        	          | list previous 10 lines |
| list *0x22e4              | list source at address |
| cd dir        	          | change current directory to \fIdir\fR |
| pwd          	            | print working directory |
| search regexpr            | forward current for regular expression |
| reverse-search regexpr    | backward search for regular expression |
| dir dirname               | add directory to source path |
| dir        	              | reset source path to nothing |
| show directories          | show source path |

</td></tr>
</table>
</div>  

<div>
<table>
<tr><th>Browsing Data</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| print expression                | print expression, added to value history |
| print/x expressionR             | print in hex |
| print array[i]@count            | artificial array - print array range |
| print $        	                | print last value |
| print *$->next                  | print thru list |
| print $1        	              | print value 1 from value history |
| print ::gx                      | force scope to be global |
| print 'basic.c'::gx             | global scope in named file (>=4.6) |
| print/x &main                   | print address of function |
| x/countFormatSize address       | low-level examine command |
| x/x &gx        	                | print gx in hex |
| x/4wx &main                     | print 4 longs at start of \fImain\fR in hex |
| x/gf &gd1                       | print double |
| help x        	                | show formats for x |
| info locals                     | print local automatics only |
| info functions regexp           | print function names |
| info variables  regexp          | print global variable names |
| ptype name                      | print type definition |
| whatis expression               | print type of expression |
| set variable = expression       | assign value |
| display expression              | display expression result at stop |
| undisplay                       | delete displays |
| info display                    | show displays |
| show values                     | print value history (>= gdb 4.0) |
| info history                    | print value history (gdb 3.5) |

</td></tr>
</table>
</div>  

<div>
<table>
<tr><th>Object File manipulation</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| file object      		| load new file for debug (sym+exec) | 
| file             		| discard sym+exec file info | 
| symbol-file object  | load only symbol table | 
| exec-file object 		| specify object to run (not sym-file) | 
| core-file core   		| post-mortem debugging | 

</td></tr>
</table>
</div>

<div>
<table>
<tr><th>Signal Control</th>
<tr><td>

| Command | Result |
| :------ | :----- |
| info signals        	  | print signal setup |
| handle signo actions    | set debugger actions for signal |
| handle INT print        | print message when signal occurs |
| handle INT noprint      | don't print message |
| handle INT stop        	| stop program when signal occurs |
| handle INT nostop       | don't stop program |
| handle INT pass        	| allow program to receive signal |
| handle INT nopass       | debugger catches signal; program doesn't |
| signal signo        	  | continue and send signal to program |
| signal 0                | continue and send no signal to program |

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
| info editing       	        rint command history (gdb 3.5) |
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

