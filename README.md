## Variables

Variables are used to store and manipulate data within shell scripts.

```bash
# Using variables
name="Alice"
age=30
echo "Hello, $name! You are $age years old."
```

## Scalar Variables:
```bash
# Scalar variables hold single values, such as integers, strings, or floating-point numbers.
name="Alice"
age=30
pi=3.1415
```

## Array Variables:
```bash
#Array variables can hold multiple values, typically indexed by integers.
fruits=("apple" "banana" "orange")
numbers=(1 2 3 4 5)
```
## Environment Variables:

```bash
# These are global variables that are predefined in the shell environment. They are accessible to all processes.
HOME=/home/user
PATH=/usr/local/bin:/usr/bin:/bin
```
## Local Variables:
```bash
# Local variables are defined within a specific shell script or function and are not accessible from outside that context.
# Inside a function
local localVar="This is a local variable"
```

### Special variables
```bash
$0      # The name of the script or shell
$1, $2  # The first and second command-line arguments
$$      # The process ID of the script
$?      # The exit status of the last command
```
## Read-Only Variables:
```bash
# Some variables, like UID or SHELL, are read-only and cannot be modified by the script.

readonly UID
readonly SHELL
```
## for loop

```bash
for item in list
do
  # Commands to be executed for each item
done
```

### sample:1
```bash
#!/bin/bash

# Define a list of numbers
numbers="1 2 3 4 5"

# Use a for loop to iterate over the list
for num in $numbers
do
  echo "Number: $num"
done
```

### sample:3
```bash
#!/bin/bash

# Use command substitution to generate a list of filenames in the current directory
for file in $(ls)
do
  echo "File: $file"
done
```
## while loop

```bash
#!/bin/bash
# A more advanced Bash shell script example

# Variables
count=1

# Looping with while
while [ $count -le 5 ]; do
  echo "Iteration $count"
  count=$((count + 1))
done
```
##  case 
```bash
#!/bin/bash

# Case statement
read -p "Enter a fruit (apple, banana, or orange): " fruit

case $fruit in
  "apple")
    echo "You chose an apple."
    ;;
  "banana")
    echo "You chose a banana."
    ;;
  "orange")
    echo "You chose an orange."
    ;;
  *)
    echo "Invalid choice."
    ;;
esac

# Function definition
greet() {
  echo "Hello, $1!"
}

# Function call
greet "Alice"
```

# operators in shell scripting:
* -eq: Equal to
* -ne: Not equal to
* -lt: Less than
* -gt: Greater than
* -ge: Greater than or equal to

In shell scripting, if statements are used to make decisions based on the evaluation of a condition. Here are some if condition examples in Bash, a common Unix-like shell:

### Basic if Statement:
```bash
Copy code
#!/bin/bash

# Check if a number is greater than 10
number=15

if [ $number -gt 10 ]; then
  echo "$number is greater than 10."
fi
if-else Statement:
```
```bash
#!/bin/bash

# Check if a number is even or odd
number=7

if [ $((number % 2)) -eq 0 ]; then
  echo "$number is even."
else
  echo "$number is odd."
fi
```

### if-elif-else Statement:

```bash

#!/bin/bash

# Check if a number is positive, negative, or zero
number=-5

if [ $number -gt 0 ]; then
  echo "$number is positive."
elif [ $number -lt 0 ]; then
  echo "$number is negative."
else
  echo "$number is zero."
fi
```
### Nested if Statements:
```bash
#!/bin/bash

# Check if a number is positive and even
number=12

if [ $number -gt 0 ]; then
  if [ $((number % 2)) -eq 0 ]; then
    echo "$number is a positive even number."
  else
    echo "$number is a positive odd number."
  fi
else
  echo "$number is not a positive number."
fi
```

### String Comparison:
```bash
#!/bin/bash

# Check if two strings are equal
string1="apple"
string2="banana"

if [ "$string1" = "$string2" ]; then
  echo "The strings are equal."
else
  echo "The strings are not equal."
fi
```

### Checking File Existence:
```bash
#!/bin/bash

# Check if a file exists
file="example.txt"

if [ -e "$file" ]; then
  echo "$file exists."
else
  echo "$file does not exist."
fi
```

# String manipulation
```bash 
string="Hello, World!"
substring=${string:0:5}
echo "Substring: $substring"
```

# Basic error handling
```bash
if [ $? -eq 0 ]; then
  echo "Command was successful."
else
  echo "Command failed."
fi
```

# Basic math operations
```bash
result=$((5 + 3))
echo "Result: $result"
```
## This is Vijay metgud from BGM #