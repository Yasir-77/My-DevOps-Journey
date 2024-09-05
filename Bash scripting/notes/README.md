## Introduction to BASH Scripting

### What is Bash Scripting?

- Bash: A command-line tool to interact with your computer.
- Bash Script: A file containing a series of commands you want the computer to execute automatically.

### Why do we learn Bash Scripting?

- Automate tasks: Save time on repetitive actions.
- Manage systems: Handle files, software installs, and system configurations.
- Boost efficiency: Get more done with less typing.

### How to write first simple script:

First create a simpole script using the **`touch`** command For example:
```
$ touch my-first-script
```
open the file using vim type:
```
$ vim my-first-script.sh
```
The first line of every file starts with a Shebang line type:

press i to inter insert mode and type:
```
#!/bin/bash

echo "Hello World!"
```
To exit the vim type: :wq!

Then chmod the script by typing:
```
chmod +x my-first-script.sh
```
To run the script type;
```
./my-first-script.sh
```

