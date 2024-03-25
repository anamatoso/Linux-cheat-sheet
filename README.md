# Linux-cheat-sheet

Welcome to the Linux Commands Cheat Sheet! This repository contains a collection of basic commands to help you navigate and utilize the command line more effectively. These commands are written in Bash shell (Bourne Again Shell) which is the default shell for most Linux distributions. It was chosen for its robust features, widespread availability, and compatibility with POSIX standards. Bash offers powerful scripting capabilities, extensive built-in commands, and is highly customizable, making it the preferred choice for Linux users and system administrators.

## Table of Contents
1. [Commands](#commands)
    - [Navigation](#navigation)
    - [File Management](#file-management)
    - [Text Manipulation](#text-manipulation)
    - [Permissions](#permissions)
    - [Process Management](#process-management)
    - - [Others](#others)
2. [Contributing](#contributing)

## Commands

### Navigation

Command | Description
------- | -----------
`cd directory_name` | Change directory to `directory_name`. 
`pwd` | Print the current working directory.
`ls` | List files and directories in the current directory.
`ls -a` | Same as `ls` but also lists hidden files and directories (the ones that start with `.`)
`find . -name pattern` | Search in the current directory tree for a file/folder with `pattern` in its name.

**Note**: If, when using `cd`, the `directory_name` is left empty or if it is a `~` then it changes to the home directory

### File Management
Command | Description
------- | -----------
`touch filename` | Create a new file named `filename`.
`mkdir directory_name` | Create a new directory named `directory_name`. (If it already exist it yields an error)
`cp source_file destination` | Copy `source_file` to `destination`.
`scp source_file destination` | Same as `cp` but between different machines.
`mv source destination` | Move or rename `source` to `destination`.
`rm filename` | Remove (delete) `filename`.
`rmdir directory_name` | Remove (delete) empty directory named `directory_name`.
`du -sh filename` | Display the size of filename (if `filename` is `*` it shows for all files/folders in directory).

**Note 1**: Use `mkdir -p directory_path` if you want to create all the parent directories or if you do not want it to give an error if the folder already exists.

**Note 2**: When using `cp`, `mv` or `rm`, include the flag `-r` if you want to copy/move/delete a folder recursively (all files and folders inside it) or if you have a file pattern to copy/move/delete.

**Note 3**: In scp, if you want to copy from/to a remote server, in the path of the source/destination write: [username]@[ip_adress]:path/to/folder , where [username] is your user in the remote server, [ip_adress] is the ip adress of the remote server. **Do not forget the colon**.

**Note 4**: Use `rm -f filename` if you do not want to yield an error if `filename` does not exist.

**Note 5**: The flags can be combined. `-f -r` is the same as `-rf`

### Text Manipulation
Command | Description
------- | -----------
`cat filename` | Display the contents of `filename`.
`nano filename` | Open `filename` in a text editor.
`grep pattern filename` | Search `filename` for lines containing `pattern`.

**Note**: Inside the `nano` editor, to save you press ctrl+o and then enter. To exit, press ctrl+x and then enter. Other commands are in the bottom of the editor.

### Permissions
Command | Description
------- | -----------
`sudo command` | Execute `command` with superuser privileges.
`ls -l` | List the files and folders of the current directory together with their permissions.
`chmod permissions filename` | Change the permissions of `filename`.

To use the chmod command, you first specify the desired permissions using symbolic notation, followed by the filename or directory you wish to modify. Symbolic notation involves using letters (**u for user, g for group, o for others**) along with symbols (**+ for adding permissions, - for removing permissions, and = for setting permissions explicitly**) to represent the permissions - read (r), write (w), execute (x). For example, the command below adds write and execute permissions of file test.txt for the user.

```bash
chmod u+wx test.txt
```

### Process Management
Command | Description
------- | -----------
`kill PID` | Terminate process with ID `PID`.
`top` | Display and manage running processes.
`htop` | Display and manage running processes but better. (type h for possible commands)

**Note**: to quit htop/top, type q

### Others
Command | Description
------- | -----------
`man command` | Shows the manual for the specified command
`echo $varname` | Displays a variable's value (eg. $SHELL)
`set -e` | When put in the beginning of a script, stops the script when it reaches an error.

## Contributing
Contributions to improve and expand this cheat sheet are welcome! Please feel free to create issues or to fork this repository, make your changes, and submit a pull request.

