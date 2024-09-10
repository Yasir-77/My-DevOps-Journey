# Bash Scripting Labs

#The Game: Bash Battle Arena 🎮

Objective: Players must complete various tasks or "missions" using Bash scripts. These tasks range from simple file manipulations to more complex system operations. The goal is to "defeat" each level by correctly solving the problem, with the ultimate aim of becoming a "Bash Master."

## Level 1: The Basics

Mission: Create a directory named Arena and then inside it, create three files: warrior.txt, mage.txt, and archer.txt. List the contents of the Arena directory.

To complete this level:

Type:
```
mkdir Arena
```
Then:
```
cd Arena
```
Then:
```
Touch warrior.txt mage.txt archer.txt
```
Then:
```
ls arena
```

## Level 2: Variables and Loops

Mission: Create a script that outputs the numbers 1 to 10, one number per line.

Create a new file called number.sh:
```
vim numbers.sh
```
Then type in the text editor:
```
#!/bin/bash

number=1

while [ $number -le 10 ]
do
        echo "number $number"
        ((number++))
done
```
Once completed make the script executable:
```
chmod +x numbers.sh
```
Then: run the script:
```
./numbers.sh
```

## Level 3: Conditional Statements

Mission: Write a script that checks if a file named hero.txt exists in the Arena directory. If it does, print Hero found!; otherwise, print Hero missing!.



































