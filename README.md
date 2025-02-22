# <img src="https://github.com/anamatoso/Linux-cheat-sheet/assets/78906907/518c85e2-4bc2-4c0d-89a4-146db7c81ce5" alt="drawing" width="50"/> Linux-cheat-sheet


Welcome to the Linux Commands Cheat Sheet! This repository contains a collection of basic commands to help you navigate and utilize the command line more effectively. These commands are written in Bash shell (Bourne Again Shell) which is the default shell for most Linux distributions. It was chosen for its robust features, widespread availability, and compatibility with POSIX standards. Bash offers powerful scripting capabilities, extensive built-in commands, and is highly customizable, making it the preferred choice for Linux users and system administrators.

## Table of Contents
1. [Commands](#commands)
    - [:compass: Navigation](#compass-navigation)
    - [:card_index_dividers: File Management](#card_index_dividers-file-management)
    - [:spiral_notepad: Text Manipulation](#spiral_notepad-text-manipulation)
    - [:busts_in_silhouette: Permissions](#busts_in_silhouette-permissions)
    - [:repeat: Process Management](#repeat-process-management)
    - [:briefcase: Others](#briefcase-others)
2. [Contributing](#contributing)

## Commands

### :compass: Navigation

Command | Description
------- | -----------
`cd directory_name` | Change directory to `directory_name`. 
`pwd` | Print the current working directory.
`ls` | List files and directories in the current directory.
`ls -a` | Same as `ls` but also lists hidden files and directories (the ones that start with `.`)
`find . -name pattern` | Search in the current directory tree for a file/folder with `pattern` in its name.

**Note**: If, when using `cd`, the `directory_name` is left empty or if it is a `~` then it changes to the home directory

---

### :card_index_dividers: File Management
Command | Description
------- | -----------
`touch filename` | Create a new file named `filename`.
`mkdir directory_name` | Create a new directory named `directory_name`. (If it already exists, it yields an error)
`cp source_file destination` | Copy `source_file` to `destination`.
`scp source_file destination` | Same as `cp` but between different machines.
`mv source destination` | Move or rename `source` to `destination`.
`ln -sf file_1 file_2` | Create a symbolic link called file_2 that points to file_1.
`rm filename` | Remove (delete) `filename`.
`rmdir directory_name` | Remove (delete) empty directory named `directory_name`.
`du -sh filename` | Display the size of the file called filename (if `filename` is `*` it shows for all files/folders in the directory).

**Note 1**: Use `mkdir -p directory_path` if you want to create all the parent directories or do not want it to give an error if the folder already exists.

**Note 2**: When using `cp`, `mv`, or `rm`, include the flag `-r` if you want to copy/move/delete a folder recursively (all files and folders inside it) or if you have a file pattern to copy/move/delete.

**Note 3**: In scp, if you want to copy from/to a remote server, in the path of the source/destination write: [username]@[ip_adress]:path/to/folder, where [username] is your user in the remote server, [ip_adress] is the IP address of the remote server. **Do not forget the colon**.

**Note 4**: Use `rm -f filename` if you do not want to yield an error if `filename` does not exist.

**Note 5**: The flags can be combined. `-f -r` is the same as `-rf`

---

### :spiral_notepad: Text Manipulation
Command | Description
------- | -----------
`cat filename` | Display the contents of `filename`.
`nano filename` | Open `filename` in a text editor.
`grep pattern filename` | Search `filename` for lines containing `pattern`.

**Note**: Inside the `nano` editor, to save you press ctrl+o and then enter. To exit, press ctrl+x and then enter. Other commands are in the bottom of the editor.

---

### :busts_in_silhouette: Permissions
Command | Description
------- | -----------
`sudo command` | Execute `command` with superuser privileges.
`ls -l` | List the files and folders of the current directory together with their permissions.
`chmod permissions filename` | Change the permissions of `filename`.

To use the chmod command, you first specify the desired permissions using symbolic notation, followed by the filename or directory you wish to modify. Symbolic notation involves using letters (**u for user, g for group, o for others**) along with symbols (**+ for adding permissions, - for removing permissions, and = for setting permissions explicitly**) to represent the permissions - read (r), write (w), execute (x). For example, the command below adds write and execute permissions of file test.txt for the user.

```bash
chmod u+wx test.txt
```

---

### :repeat: Process Management
Command | Description
------- | -----------
`screen` | Useful to let processes running even when you disconnect from the server.
`kill PID` | Terminate process with ID `PID`.
`top` | Display and manage running processes.
`htop` | Display and manage running processes but better. (type h for possible commands)

**Note 1**: To create a new screen use `screen -S [name]`. To detach from the screen click `ctrl`+`a`+`d`. To resume, type `screen -r [name]`. To list all screens available use `screen -ls`. To delete a screen, connect to it through the resume command and then type `exit`. Sometimes, it might be useful to remotely detach from a screen, using `screen -d [name]`.

**Note 2**: to quit htop/top, type `q`.

---

### :briefcase: Others
Command | Description
------- | -----------
`man command` | Shows the manual for the specified command
`echo $varname` | Displays a variable's value (eg. $SHELL)
`set -e` | When put in the beginning of a script, it stops that script from continuing to run after it yields an error.
`\|` | If you want to run two sequential commands, put a pipe in between them like so `command_1 \| command_2`.

## Contributing
Contributions to improve and expand this cheat sheet are welcome! Please feel free to create issues or to fork this repository, make changes, and submit a pull request.

