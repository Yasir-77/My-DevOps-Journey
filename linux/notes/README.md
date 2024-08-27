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

To add text into a file. Run **`echo`** command. An example of how to add "Hello World" into an already made file.txt would be:
```
$ echo "Hello World" > file.txt
```
To add another line of text without removing any content already in the file simply use >> instead of >:
```
$ echo "Test" >> file.txt
```

To search for specific content of text within a file. Run command **`grep`**. An example of how to search for the word "Hello" in the already made file.txt would be:
```
$ grep "Hello" file.txt
```

To search up all the contents in a file. Run the **`cat`** command. 
```
$ cat file.txt
```

This should show the first line reading "Hello World" and the seconf line reading "Test"

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





