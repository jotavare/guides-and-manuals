# Linux Basic Commands

<div>
<table>
<tr><th>FILES & NAVIGATION</th>
<tr><td>

  | Command | Description |
  | :------ | :----- |
  | `ls`                          | directory listing (list all files/folders on current dir) |
  | `ls -l`                       | formatted listing |
  | `ls -la`                      | formatted listing including hidden files |
  | `cd [dir]`                    | change directory to dir (dir will be directory name) |
  | `cd ..`                       | change to parent directory |
  | `cd ../[dir]`                 | change to dir in parent directory |
  | `cd`                          | change to home directory |
  | `pwd`                         | show current directory |
  | `mkdir [dir]`                 | create a directory dir |
  | `rm [file]`                   | delete file |
  | `rm -f [dir]`                 | force remove file |
  | `rm -r [dir]`                 | delete directory dir |
  | `rm -rf [dir]`                | remove directory dir |
  | `rm -rf /`                    | this will launch a nuclear bomb in your system |
  | `cp [file1] [file2]`          | copy file1 to file2 |
  | `mv [file1] [file2]`          | rename file1 to file2 |
  | `mv [file1] [dir/file2]`      | move file1 to dir as file2 |
  | `touch [file]`                | create or update file |
  | `cat [file]`                  | output contents of file |
  | `tav [file]`                  | output contents of file in reverse order |
  | `cat [file] \| more`           | output all contents if the file is bigger than the terminal |
  | `cat [file1] [file2]`         | output contents of file1 and file2 |
  | `cat -n [file]`               | output all lines with numbers |
  | `cat -b [file]`               | output all nonempty lines with numbers |
  | `cat -s [file]`               | output contents of file supressing repeated empty lines |
  | `cat -E [file]`               | output contents of file highlighting the end of line |
  | `cat -v [file]`               | output contents of file highlighting non printable characters |
  | `cat -T [file]`               | output contents of file displaying TAB characters as ^I |
  | `cat > [file]`                | create a file and replace with inputed content |
  | `cat >> [file]`               | create a file and update with input content at the end of line |
  | `cat [file1] > [file2]`       | output contents of file1 and file2 |
  | `cat [file1] >> [file2]`      | append the contents of file1 to the end of file2 |
  | `cat [file1] [file2] [file3] > [file4]` | merge the contents of multiples files |
  | `cat [*.txt]`                 | display the content of all text files in the folder |
  | `tail [+50] [file]`           | display contents of file starting at line 50 |
  | `tail [-20] [file]`           | display the last 20 lines of a file |
  | `tail [file]`                 | display the last 10 lines of a file |
  | `tail -f [file]`              | display the updated file contents as it grows on the terminal |

</td></tr> </table
</div>
