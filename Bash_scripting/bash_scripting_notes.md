# Comprehensive Bash Scripting Notes

## 1. Introduction and Basics

A Bash script is a plain text file containing a series of commands.

**The Shebang (`#!`)**
Always start your bash script with a shebang to specify the interpreter:

```bash
#!/bin/bash
```

**Executing a Script**

1. Make the script executable: `chmod +x script.sh`
2. Run it: `./script.sh`

## 2. Variables

Variables in Bash do not require declaration or typing.

- **No spaces** around the equals sign `=`.

```bash
# Assignment
NAME="Alice"
AGE=30

# Usage (use $ or ${})
echo "Hello, $NAME. You are ${AGE} years old."

# Command Substitution
CURRENT_DATE=$(date)
echo "Today is $CURRENT_DATE"
```

## 3. Special Variables and Arguments

Bash provides built-in variables for script arguments and state.

- `$0` - Name of the script
- `$1, $2, ... $9` - Arguments passed to the script
- `$#` - Total number of arguments
- `$@` - All arguments as a list
- `$?` - Exit status of the most recently executed command (`0` means success)
- `$$` - Process ID (PID) of the current script

## 4. Input / Output

**Output:** `echo` and `printf`

```bash
echo "Simple output"
echo -e "Output with \n newline"
```

**Input:** `read`

```bash
echo "Enter your name:"
read USER_NAME
echo "Hello $USER_NAME"

# Read with a prompt shortcut
read -p "Enter your age: " USER_AGE
```

## 5. Conditionals (If/Else)

```bash
if [ "$AGE" -lt 18 ]; then
    echo "Minor"
elif [ "$AGE" -ge 18 ] && [ "$AGE" -lt 65 ]; then
    echo "Adult"
else
    echo "Senior"
fi
```

### Common Test Operators

**Numbers:**

- `-eq` (equal), `-ne` (not equal), `-lt` (less than), `-le` (less eq), `-gt`, `-ge`

**Strings:**

- `=` (equal), `!=` (not equal), `-z` (is empty), `-n` (is not empty)

**Files:**

- `-e` (exists), `-f` (is regular file), `-d` (is directory), `-r` (readable), `-w` (writable), `-x` (executable)

## 6. Loops

**For Loop**

```bash
# Iterating over a list
for color in red green blue; do
    echo "Color: $color"
done

# Iterating over a range
for i in {1..5}; do
    echo "Number: $i"
done
```

**While Loop**

```bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    ((count++))
done
```

## 7. Arrays

```bash
# Declaration
MY_ARRAY=("Apple" "Banana" "Cherry")

# Accessing
echo "First element: ${MY_ARRAY[0]}"
echo "All elements: ${MY_ARRAY[@]}"
echo "Number of elements: ${MY_ARRAY[#]}"

# Adding element
MY_ARRAY+=("Orange")
```

## 8. Functions

Functions help organize and reuse code.

```bash
# Definition
greet() {
    local NAME=$1 # local scope variable
    echo "Hello, $NAME!"
}

# Calling a function (pass arguments after space)
greet "Alice"
```

## 9. Error Handling and Best Practices

It is a good practice to set strict execution modes at the top of your scripts.

```bash
#!/bin/bash
set -e          # Exit immediately if a command exits with a non-zero status.
set -u          # Treat unset variables as an error when substituting.
set -o pipefail # The return value of a pipeline is the status of the last command to exit with a non-zero status.
```

**Debugging**
You can run a bash script in debug mode using:

```bash
bash -x script.sh
```

Or temporarily inside the script:

```bash
set -x # Enable debug mode
# code here
set +x # Disable debug mode
```
