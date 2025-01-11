# Bash Built-in Commands Reference

This document provides a comprehensive reference for Bash built-in commands. It explains each command's function and includes basic usage examples. Ideal for beginners and experienced shell users.

## Table of Contents

- [Introduction](#introduction)
- [Basic Commands](#basic-commands)
- [Flow Control](#flow-control)
- [Job Control](#job-control)
- [File and Directory Management](#file-and-directory-management)
- [Process Management](#process-management)
- [Networking and I/O](#networking-and-io)
- [Variable Management](#variable-management)
- [Scripting Utilities](#scripting-utilities)
- [Conclusion](#conclusion)

---

## Introduction

Bash (Bourne Again SHell) includes many built-in commands that facilitate shell scripting, job control, process management, and more. This document provides a structured overview of these built-ins.

---

## Basic Commands

### `echo`
**Description:** Prints text to standard output.  
**Usage:**
```bash
echo "Hello, World!"
echo -n "No newline at end"
```

### `pwd`
**Description:** Prints the current working directory.  
**Usage:**
```bash
pwd
pwd -P   # Avoids symbolic links
```

### `cd`
**Description:** Changes the current working directory.  
**Usage:**
```bash
cd /path/to/directory
cd ~  # Move to home directory
cd -  # Go back to the previous directory
```

### `ls`
*(Not a built-in, but essential in shell usage.)*  
**Description:** Lists directory contents.  
**Usage:**
```bash
ls
ls -lah  # Detailed view
```

---

## Flow Control

### `if`
**Description:** Conditional execution based on an expression.  
**Usage:**
```bash
if [ -f "file.txt" ]; then
  echo "File exists"
else
  echo "File does not exist"
fi
```

### `case`
**Description:** Matches a value against multiple patterns.  
**Usage:**
```bash
case "$1" in
  start) echo "Starting...";;
  stop) echo "Stopping...";;
  *) echo "Unknown command";;
esac
```

### `for`
**Description:** Loops through a list of values.  
**Usage:**
```bash
for i in {1..5}; do
  echo "Iteration $i"
done
```

### `while`
**Description:** Loops while a condition is true.  
**Usage:**
```bash
while [ "$var" != "exit" ]; do
  read -p "Enter something: " var
done
```

---

## Job Control

### `jobs`
**Description:** Lists background jobs.  
**Usage:**
```bash
jobs
```

### `bg`
**Description:** Resumes a suspended job in the background.  
**Usage:**
```bash
bg %1
```

### `fg`
**Description:** Brings a background job to the foreground.  
**Usage:**
```bash
fg %1
```

### `kill`
**Description:** Sends a signal to terminate a process.  
**Usage:**
```bash
kill -9 <PID>
```

---

## File and Directory Management

### `pushd`
**Description:** Saves the current directory and changes to a new one.  
**Usage:**
```bash
pushd /path/to/dir
```

### `popd`
**Description:** Returns to the last saved directory.  
**Usage:**
```bash
popd
```

---

## Process Management

### `exec`
**Description:** Replaces the current shell with another command.  
**Usage:**
```bash
exec bash
```

### `trap`
**Description:** Executes a command when a signal is received.  
**Usage:**
```bash
trap "echo 'Caught SIGINT'" SIGINT
```

### `wait`
**Description:** Waits for background processes to complete.  
**Usage:**
```bash
wait <PID>
```

---

## Networking and I/O

### `read`
**Description:** Reads input from the user.  
**Usage:**
```bash
read -p "Enter your name: " name
echo "Hello, $name"
```

### `printf`
**Description:** Formats and prints output (like in C).  
**Usage:**
```bash
printf "Hello, %s!\n" "$USER"
```

---

## Variable Management

### `export`
**Description:** Makes a variable available to child processes.  
**Usage:**
```bash
export PATH="$PATH:/new/path"
```

### `unset`
**Description:** Removes a variable.  
**Usage:**
```bash
unset var_name
```

### `declare`
**Description:** Declares variables with attributes.  
**Usage:**
```bash
declare -i num=5
```

---

## Scripting Utilities

### `test`
**Description:** Evaluates a condition.  
**Usage:**
```bash
test -f "file.txt" && echo "File exists"
```

### `source`
**Description:** Reads and executes commands from a file.  
**Usage:**
```bash
source script.sh
```

### `true` / `false`
**Description:** Always return success (`0`) or failure (`1`).  
**Usage:**
```bash
true  # Returns 0
false # Returns 1
```

---

## Conclusion

This document provides a summary of important Bash built-ins. For more details, refer to:
- The Bash manual: `man bash`
- Built-in help: `help <command>`
- Online documentation: [GNU Bash Manual](https://www.gnu.org/software/bash/manual/)

---

## License

This document is provided under the [MIT License](LICENSE).
