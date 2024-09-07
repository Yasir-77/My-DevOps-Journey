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
$ touch first_script.sh
```
open the file using vim type:
```
$ vim first_script.sh
```
The first line of every file starts with a Shebang line type:

press i to inter insert mode and type:
```
#!/bin/bash

echo "Hello World!"
```
To exit the vim type: :wq!

Then add executable to the script by running the chmod command:
```
chmod +x first_script.sh
```
To run the script type;
```
./first_script.sh
```

The Shebang line always starts with a # followed by an !, it specifies the interpreter/shell that handles the script, it enables consistent executional scripts across different environmenrt regardless of whatever shell is used and you can specifiy different interpreters fopr different types of scripts. It is always the first linjhe of the script.

### How to write comments in the file?

To write comments that you dont want appearing in the file for others simply use the # at the beginning of the line. If you want to write multiple lines of comment write 

line 1: :  '

Line 2 to 10 : Comments ........

Line 11: '

Comments can also be used when debugging or when not wanting to run a line of code.

Adding comments to your script improves readability, better collaboration with team and help ensures scripts purpose remains evidents

### How to run scripts from anywhere

The file first_script.sh can only be run in its current directory by us ./first_script.sh to run the file from anywhere without specifying the Path.

First Place the file in one of the directiories thats in the PATH enviornment variable to do this type:
```
echo $PATH
```
This will give you a list of PATHS. The PATH is an envirmonet variable that tell the shell which directories to search, to search for executable files in response to commands.

A lsit of several directories seperated by colons will show, any executable file placed in one will run from anywhere. To place the first_file.sh folder in the directory use the **`sudo mv`** command followed by the file name followed by the selected PATH in this case /usr/local/bin followed by what you want to name the file in this case greet. For example:

```
sudo mv first_script.sh /usr/local/bin/greet
```

Then add executables on the script again using chmod command:
```
sudo chmod +x /usr/local/bin/greet
```
Now you can type greet anywhere and "Hello World" will appear.

### Variables

In Bash, you can define variables without any special symbols or keywords. Just assign a value to a name, but do not use spaces around the = sign. For example to assign the variable name to Yasir type:
```
name="Yasir"
```
To use the value of a variable, you need to prefix the variable with a **`$`**
```
echo "Hello,$name"
```
The output would be Hello Yasir

### Parameters

Parameters are values you pass to a script when you execute it. These parameters allow you to make your script dynamic, flexible, and capable of handling various inputs.

When you pass arguments to a Bash script, they are stored in special variables called positional parameters. These variables are $1, $2, $3, etc., representing the first, second, and third arguments passed to the script.
First cretea a file in this case a file called script.sh was created. Then set the parameters in the text. 
```
#!/bin/bash

echo "First parameter: $1"
echo "Second parameter: $2"
echo "Third parameter: $3"
```
When you run the script like this
```
./script.sh hello hi
```
It will output:
```
parameter 1: hello
parameter 2: hi
parameter 3:
```
If we were to add a third parameter on the line ./script.sh  hello hi (3rd parameter), it will poutput the 3rd parmeter.

To access all parameters passed into a script use the following tect in the file:
```
#!/bin/bash

echo "First parameter: $1"
echo "Second parameter: $2"
echo "Third parameter: $3"

echo "All Parameters: $@"
```
It will output:
```
parameter 1: hello
parameter 2: hi
parameter 3:
All Parameters: hello hi 
```

### Arithmetic expansion

Arithmetic expansion in Bash allows you to perform arithmetic operations directly within your scripts. You can use arithmetic expressions inside $(( ... )), which allows basic and complex mathematical operations.

some examples:

e.g. 1
```
#!/bin/bash
num1=5
num2=10
result=$((num1 + num2))  
echo "Sum of $num1 + $num2 is: $result"
```

When you run your script it will output:
```
sum of 5 and 10 is: 15
```

e.g. 2
```
#!/bin/bash
length=5
width=10
area=$((length * width))
perimeter=$((2 * (length + width))

echo "Rectangle area: $area"
echo "Rectangle perimeter: $perimeter"
```
When you run your script it will output:
```
Rectangle area: 40
Rectangle permiter: 25
```
### Arithmetic expansion with parameters

Arithmetic expansion with parameters allows us to take onput from, the user or from the command and arguments and perform calculations based on those values.

In this instance the text in the file would be:
```
#!/bin/bash
length=$1
width=$2
area=$((length * width))
perimeter=$((2 * (length + width))

echo "Rectangle area: $area"
echo "Rectangle perimeter: $perimeter"
```
Changing the length and width to parameters means that any numbers you put in the script.

For example when you run the script: 
```
./arithmetic.sh 4 5
```
The output will be:
```
Rectangle area: 20
Rectangle perimeter: 18
```

#!/bin/bash

age=25

if [ $age -gt 18 ]
then
	echo "You are an adult!"
fi

### if statements

In Bash scripting, if statements are used to execute a block of code based on a condition. The basic structure of an if statement can be extended to handle multiple conditions and complex logic.

The general stucture is:
```
#!/bin/bash

if condition
then
	# code block to be executed
fi
```
conditions in if statements are formed using comparison operators for example:
- eq = equals
- ne = npot equals to
- lt = less than or equal to
- ge = greater than or equal to

If statments become more powerful when combined with logical operators for example:
- && = AND
- || = OR

These can be used to create more complex conditions.

Some examples:

e.g.1

```
#!/bin/bash

age=25

if [ $age -gt 18 ]
then
	echo "You are an adult!"
fi

```
This script should printt "You are an adult".

e.g.2

```
#!/bin/bash

grade=85

if [ $grade -ge 90 ] && [ $grade -le 100] 
then
	echo "Excellent"
fi

```
The script will print nothing as 85 doesnt fall in this range, however if **`grade=95`** then the script would print "Excellent".

e.g.3 

To compare strings operators that are used are:

- == which is equals to
- != which is not equals to

```
#!/bin/bash

name="Alice"

if [ $name == "Alice"] 
then
	echo "Hello, Alice"
fi

```
The script in this case will print "Hello, Alice". If any other name is the variable nothing will appear.

### else and elif

The else clause provides an alternative code block to be executed when the if condition evaluates to false. It provides an alternative path in your scripts flow offering flexibility and versatility.

The structure of an else clasue:
```
#!/bin/bash

if condition
then
	# code block if condition is true
else
  # code block if condition is false
fi
```

Some examples:

e.g.1
```
#!/bin/bash

age=15

if [ $age -gt 18 ]
then
	echo "You are an adult!"
else
  echo "You are not an adult!"
fi
```
The script will print "You are not an adult!"

e.g.2
```
#!/bin/bash

score=85

if [ $score -ge 90 ]
then
	echo "Excellent!"
elif [ $score -ge 80 ]
then
  echo "Good!"
else
  echo "Better luck nect time"
fi
```

The elif clause allows us to add another condition if nthe first condition is false. The else clause only executes when the condition for the if statements arent met

With the score being 85 the script will print "Good!".

### Nested if statements


Nested if statements allow you to check multiple conditions in a more complex manner. When you nest if statements, an inner if block is executed only if the outer if condition is true. This is useful when decisions depend on more than one condition.

For Example:
```
#!/bin/bash

age=18
grade=85

if [ "$age" -gt 18 ]; then
    echo "You are eligible based on age."
  if [ "$grade -ge 80 ]; then
    echo "You are eligible based on grade."
    echo "Congrats! You are eligible for scholarship"
  else
    echo "sorry your grade is not high enough"
  fi 
else
   echo "sorry, you are not eligible"
  fi
```

In this case the response will say "sorry you are not eligible" this is due to the age, however if the age=19, the script will read "You are eligible based on age. You are eligible based on grade. Congrats! you are eligible for scholarship".

### While loops

While loops allow you to repeatedly execute a block of code as long as a specified condition is true. These loops are useful when you don't know in advance how many iterations you'll need, and the loop continues until a condition is no longer met.

The general structure of a while loop is:
```
#!/bin/bash

while condition
do
	# code to be executed
done
```

Some examples:

e.g.1
```
#!/bin/bash

count=1

while [ $count -le 5 ]
do
	echo "count: $count"
        ((count++))  
done
```
When this is run the count will continue until it reaches 5, once it does the loop ends. ((count++)) adds 1 for each iteration of this while loop.  The script will show:
```
count: 1
count: 2
count: 3
count: 4
count: 5 
```

e.g.2 
```
#!/bin/bash

fruits=("apple" "banana" "orange") 
index=0 

while [ $index -lt ${#fruits[@]} ]
do
	echo "Fruit: ${fruits[$index]}" 
        ((index++))  
done
```

When running the script the output would be:
```
Fruit: apple
Fruit: banana
Fruit: orange
```

Explaining the code:


fruits=("apple" "banana" "orange") - This line declares an array called fruits with three elements: "apple", "banana", and "orange".

index=0  - A variable called index is initialized with a value of 0. This will be used to keep track of the current position (or index) as we loop through the array.

while [ $ index -lt ${#fruits[@]} ] - This is a while loop that continues as long as the condition is true.
Condition: [ $ index -lt ${#fruits[@]} ] checks if the value of index is less than the number of elements in the array

echo "Fruit: ${fruits[$index]}" -  #This line prints the current fruit in the array.
${fruits[$index]} accesses the element in the array at the position specified by index. For example, if index is 0, it accesses fruits[0], which is "apple".
        
((index++))  #This is a shorthand for incrementing the value of index by 1.


  















