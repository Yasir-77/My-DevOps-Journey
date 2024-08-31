# Linux notes

### What is Linux?
Linux is an open source operating system like Windows and macOS but very different.

### Why use Linux?

- Linux is known for its flexibility, customisation and security features, which makes it popular in both professional and personal environments.

- Open Source Nature - Linux is open source, which means its source code is freely available to anyone. This allows users to modify, distribute, and even sell modifications to the OS under their own terms. 

- Cost-Effectiveness - Most Linux distributions are free to download and use, which can result in significant cost savings, especially for businesses and developers who need to deploy multiple machines.

- Customizability - Linux is highly customizable. Users can modify everything from the kernel (the core of the operating system) up to the desktop environment, allowing for a tailored experience that meets specific needs or preferences.

- Security -  Linux is considered highly secure compared to many other operating systems. Its permission and user role features, along with a strong community and frequent updates, help keep systems secure from malware and other vulnerabilities.

- Stability and Reliability - Linux systems are known for their stability and reliability. They can run for years without needing a reboot, which is a critical requirement for servers and continuous operation systems.

- Community Support - The Linux community is one of its greatest assets. A large, active community means users often get rapid support and help through forums, blogs, and community-driven projects.


There are many different versions of Linux called distributions some examples include Ubuntu, Fedora and CentOs.

### Why are there different distributions?

- Different distributions cater to differetn needs, which help beginners choose which one fits their requirements.

## Basic Linux commands

### What are commands?

Commands are textual instructions that tell the operating system what to do, they are usually typed into the terminal and are case sensitive. Commands have various options and arguments that can modify their behaviour and have instructions via a manual.

### Examples of basic Linux commands:

To print the present working directory. Run **`pwd`** command.
  
To see the contents of the directory. Run **`ls`** command.

To change the current directory. Run **`Cd`** command.  

To make (or) create a directory. Run **`mkdir`** command.

To remove (or) delete a directory. Run **`rmdir`** command.

To make (or) create a file. Run **`touch`** command.

To remove (or) delete a file. Run **`rm`** command.  

### What is the structure of a command?

The command itself, options and an arguemnt e.g. ls -a.

In this example command is **`ls`**, option is **`-a`** and argument is **`.`**

In this case the **`-a`** means that you are using the ls command to list the contents in the current directory but in this case all the contents including the hidden files and directories.

In this case the **`.`** means that the argument is in the current working directory.

### More examples of Linux commands

### - Echo command

To add text into a file. Run **`echo`** command. An example of how to add "Hello World" into an already made file.txt would be:
```
$ echo "Hello World" > file.txt
```
To add another line of text without removing any content already in the file simply use >> instead of >:
```
$ echo "Test" >> file.txt
```

If the file doesnt exist, the echo command can also be used to create a file. An example of creating a file2.txt would be:
```
$ echo "This is the second file" >> file2.txt
```

### - grep command

To search for specific content of text within a file. Run command **`grep`**. An example of how to search for the word "Hello" in the already made file.txt would be:
```
$ grep "Hello" file.txt
```

### - cat command

To search up all the contents in a file. Run the **`cat`** command. 
```
$ cat file.txt
```

The cat command could also be used to combine the contents of 2 files together creating a new file also. For Example:
```
$ cat file.txt file2.txt > combined.txt
```

To transfer the contents of one file to another file without creating a new file can be done using the cat command. For example transferring everthing in file2.txt to file.txt could be done by:
```
$ cat file2.txt >> file.txt
```

### - head and tail command

The **`head`** command displays the first part of files. By default, it shows the first 10 lines of a file. For example lets say filename.txt has 20 lines. Typing the following would show the first 10 lines:
```
$ head filename.txt
```

To display the first n lines only, use the head command in the following way. The number after -n stating how many lines to show, so for first 5 lines:
```
$ head -n 5 filename.txt
```

The **`tail`** command displays the last part of files. By default, it shows the last 10 lines of a file. 
```
$ tail filename.txt
```

To display the last n lines only, use the tail command in the following way. The number after -n stating how many lines to show, so for last 5 lines:
```
$ tails -n 5 filename.txt
```

Both head and tail can be used in combination with other commands using pipes (|). For example, you might want to view the last 10 lines of a file and then the first 5 lines of that result:

```
$ tail -n 10 filename.txt | head -n 5
```

## The SHELL

### What is the SHELL

The SHELL is a user interface that provides access to the operating system services, the layer between the user and the core of the operating system. Translates commands into actions.

### Types of SHELLS

- Bash shell

- Csh/Tcsh Shell

- Ksh Shell

- Zsh Shell

- Fish

Each shell has its own features and capabilities but all serve the same purpose to provide a userface that allows access to the operating system.

The default shell for most operating systems is the bash shell, to check this type:
```
$ echo $SHELL
```

To install a shell, type the following command **`sudo apt-get install`** followed by the desired **`<shell_name>`**. For example to install zsh shell type the following:
```
$ sudo apt install zsh
```

To then switch to the zsh shell just type the zsh command **`zsh`**.

To set zsh as the default shell type the following:

```
$ chsh -s /bin/zsh
```

Then refresh the instance and restart the windows powershell.

## File management commands

### - cp command

The **`cp`** command is used to copy files and directories from one location to another. It stands for copy. For example you wanted to copy a file called myfiles1.txt to myfiles2.txt simply write the following:

```
$ cp myfile1.txt myfile2.txt

```

If file2.txt does not exist, it will be created.

When trying to use a cp command to copy a directory, use -r before writing which file to copy. -r : Copy directories recursively. This is required when copying directories. For example if you want to make a copy of my_directory type:
```
$ cp -r my_directory my_directory_copy

```

### - mv and rm commands

The **`mv`** command is used to move or rename files and directories. The mv command stands for move, but it functions as both a move and rename command, depending on how it is used.

To rename a file use the mv command and write the name of the old file and then the name of the new file. For example changing the name from oldname.txt to newname.txt type:
```
$ mv oldname.txt newname.txt

```

When moving a file into a directory simply type mv [File_name] [Directory_name]. For example newname.txt needs to be moved into New_directory type:
```
$ mv newname.txt new_directory

```

The **`rm`** command is used to remove (delete) files and directories. It stands for remove and is a powerful command because it deletes files and directories permanently, without moving them to a trash or recycle bin.

To remove a file simply type rm [File_name]. For example to reemove newname.txt type:
```
$ rm newname.txt

```

To remove a directory and the contents inside it type -r [directory_name] after the rm command. For example to delete new_directory type:
```
$ rm -r new_directory

```

### - mkdir, rmdir and rm -r commands

As already mentioned **`mkdir`** is used to make directories. 

To make nested/parent directories simply type mkdir and add -p followed by [Directory1/directory2/directory3] For example you wanted components directory in a src directory in a project directory simply type the following:
```
$ mkdir -p project/src/components

```

To list all files and subdirectories in the current directory type **`ls -R`** [Directory_name]. For example to list the directories created above under the project directopry type:
```
$ ls -R project

```

As already mentioned **`rmdir`** is used to delete empty directories.

In the example above project and src directories cant be removed using rmdir as they have subdirectories. The components direcotory has no subdirectory so to remove the directory type:
```
$ rmdir project/src/components

```

The **`rm -r`** command is used to remove directories and their contents recursively. This means it will delete the specified directory, all files within it, and all subdirectories and their contents. To elete the project directory and all the subdirectories and the content within type:
```
$ rm -r project

```

## VIM

To start vim, type **`vim`** followed by a file name in the terminal: For example to start vim in example.txt type:
```
$ vim example.txt

```
If the file filename.txt does not exist, Vim will open a new empty file. If it exists, Vim will open it for editing.

vim has multiple modes but the 3 most important ones are:

- command mode: This mode is used for entering commands, such as saving a file or exiting Vim. You enter Command-Line Mode by pressing : in Normal Mode. This is also the default mode when you enter vim.
  
- insert mode: In this mode, Vim behaves like a standard text editor, allowing you to input and edit text. You can enter Insert Mode from Normal Mode by pressing i.

- visual mode: This mode allows for text selection using the keyboard. You can enter Visual Mode by pressing v in Normal Mode.

### Navigating in Vim 

h: Move the cursor left

j: Move the cursor down

k: Move the cursor up

l: Move the cursor right

0: Move to the beginning of the line

$: Move to the end of the line

gg: Move to the beginning of the file

G: Move to the end of the file

w: Move forward to the next word

b: Move backward to the previous word

### Editing in vim

i: Enter Insert Mode before the cursor

a: Enter Insert Mode after the cursor

o: Insert a new line below the current line and enter Insert Mode

O: Insert a new line above the current line and enter Insert Mode

x: Delete the character under the cursor

dd: Delete the current line

yy: Yank (copy) the current line

p: Paste the yanked or deleted text after the cursor

u: Undo the last change

Ctrl + r: Redo the undone change

### Saving and Exiting

To save and exit the file, use the Command-Line Mode:

:w: Save the current file

:q: Quit Vim (only works if no changes have been made)

:wq: Save and quit Vim

:q!: Quit Vim without saving changes

## Sudo command

The sudo command stands for "superuser do." It allows a permitted user to execute a command as the superuser (root) or another user, as specified by the security policy. The sudo command is typically used to perform tasks that require administrative privileges.

Examples of using sudo would be to run a command as a root. For example:
```
$ sudo apt-get update

```
This command runs apt-get update with root privileges, allowing you to update packages.

To edit protected files youll also need to use a sudo command. For example /etc/host is a protected root user file. To edit the file type:
```
$ sudo vim /etc/hosts

```

This command opens the /etc/hosts file with the vim text editor using root privileges, allowing you to edit the file.

When you need to switch to the root user to perform administritive taskts type the following:
```
$ sudo su

```
This is used when you are running multiple commands that require super user permissions.

## rm -rf / **Very dangerous command**

The **`rm -rf /`** command is a very dangerous command and shoulbe be avoided. 

### What does the command do?

Delete All Files and Directories: It will recursively delete every file and directory on the filesystem. This includes system files, user files, and everything else stored on the device

No Confirmation: Because of the -f option, rm will not ask for any confirmation before deleting files, regardless of their permissions or whether they are protected or critical system files.

### Potential Consequences

System Crash: The command will start deleting essential system files and directories immediately, causing the system to become unstable and eventually crash.

Data Loss: All data on the system will be deleted, including personal files, system files, configurations, and applications. This data loss is typically unrecoverable without backups.

Unrecoverable State: After executing this command, the operating system will not function properly, if at all. The system would require a complete reinstall, and all data would be lost unless backed up elsewhere.

## Users

To create a new user type **`sudo useradd`** the the new username. For example to creat a user called newuser type:
```
$ sudo useradd

```

To set a password for the user type **`sudo passwd`** then the username. For example to add a password to the username newuser type:
```
$ sudo passwd newuser

```

You would then need to type in a password and confirm the password again

To switch to the new user use the **`su`** command followed by - , followed by the user. For example to switch to the newuser created type:
```
$ su - newuser

```


You will then need to type the password you created.

To give the newuser sudo privellages, first exit the newuser by typing exit then type the following:
```
$sudo usermod -aG sudo newuser
```


To check if this is complete the newuser should be able to read the contents of the root directory by typing:
```
$sudo ls /root
```
The directories should then be listed, if not permission will be denied.


To remove sudo privellages, you would need to leave the new user by typing exit, this will take you to the ubunto user then type:
```
$sudo deluser newuser sudo
```

## Groups:

To create a new group run the command **`sudo groupadd`** followed by [group-name]. For example to create a new devops group type:
```
$sudo groupadd devops
```
To verify that thos has been created type the command:
```
$cat /etc/groups
```
To add users to the group that has been created the command **`sudo usermod`** is used followed by [-aG] followed by the [group-name] followed by the [user-name]. For exxample to add newuser to the devops group type:
```
$sudo usermod -aG devops newuser
```
To remove a user from the group use the comman **`sudo gpasswd`** followed by [-d] followed by the [user-name] followed by [group-name] for example to remove the newuser from the devops group type:
```
$sudo gpasswd -d newuser devops
```
To delete a group use the command **`sudo groupdel`** followed by the [group-name], for example to delete the devops group type:
```
$sudo groupdel devops
```
Users can be in multiple groups, to add users into multiple groups the command **`sudo usermod`** followed by [-aG] followed by [group-name1,group-name2] followed by the [user-name]
Fore example to add a newuser into groups called group1 and group2 (these havent beeen created) type:
```
$sudo usermod -aG group1,group2 newuser
```

## File permissions
File permissions are represented by a combination of three types of permissions for three categories of users:

Types of Permissions:

- Read (r): Allows viewing the contents of a file or directory listing.
- Write (w): Allows modifying the contents of a file or creating/deleting files within a directory.
- Execute (x): Allows running a file as a program/script or accessing a directory's contents.

Categories of Users:

- Owner (u): The user who owns the file.
- Group (g): Users who are members of the file's group.
- Others (o): All other users.

A file's permissions can be viewed with the **`ls -l`** command, which shows them in the format:

-rwxr-xr--

Here, the first character represents the file type (e.g., - for a regular file, d for a directory). The next nine characters are grouped in sets of three, representing the permissions for the owner, group, and others respectively:

rwx (owner): Read, write, and execute.

r-x (group): Read and execute, no write.

r-- (others): Read only, no write or execute.

### Octal Representation

Permissions can also be represented numerically:

- Read (r) = 4
- Write (w) = 2
- Execute (x) = 1

Each set of permissions is represented by a single digit that is the sum of its individual permissions:

rwx = 4 + 2 + 1 = 7

r-x = 4 + 0 + 1 = 5

r-- = 4 + 0 + 0 = 4

So, the permission rwxr-xr-- would be represented numerically as 754.

## Chmod command: symoblic and numeric

Using Symbolic Notation

Symbolic notation uses letters to modify permissions:

- u: User (owner)
- g: Group
- o: Others

You can add, remove, or set specific permissions using +, -, or =:

- +: Adds a permission.
- -: Removes a permission.
- =: Sets a specific permission, overriding the current setting.

Examples:

To grant the user execute permissions, groups read permissions and remove write permissions from others on file example.txt type the following:
```
$chmod u+x,g+r,o-w example.txt
```
Set Read and Write Permissions for User, and Read for Group and Others Type:
```
$chmod u=rw,go=r example.txt
```

Using Octal notation 

Set Permissions to rwxr-xr-x (755) for file example.txt:
```
$chmod 755 example.txt
```

Gives the owner all permissions (read, write, execute), and read and execute permissions to group and others.

## Changine file/direcorty ownership for user/group

To change the owner of a file or directory the command **`sudo chown`** is used followed by the [new-user] followed by [file-name]. For example to change the owner to newuser of the file called example.txt type:
```
$sudo chown newuser example.txt
```

To change the group of a file or directory run the command **`sudo chgrp`** followed by the [new-group] followed by the [file-name]. For example to change the group to group1 of the file called example.txt type:
```
$sudo chgrp group1 example.txt
```

To change both the owner and the group the command **`sudo chown`** command is used followed by [new-user:new-group] followed by the [file-name]. For example to change the user and group to newuser and group1 at the same time for file example.txt type:
```
$sudo chown newuser:group1 example.txt
```
To Change Ownership of a Directory and Its Contents the command **`sudo chown`** is used, followed by [-R] followed by [new-user:new-group] followed by the [directory-name]. For example to change the user and group to newuser and group1 at the same time for a directory called my_directory_copy (hasnt been created) type:
```
$sudo chown -R newuser:group1 my_directory_copy  
```






























































