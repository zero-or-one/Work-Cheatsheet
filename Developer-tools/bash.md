# Bash
## Definition
Bash (Bourne Again SHell) is a Unix shell and command language written as a free software replacement for the Bourne shell. Bash commands are used to interact with the operating system to perform a variety of tasks, such as file manipulation, program execution, and system administration.


## 📂 Basic Bash Commands

### 1. **`ls`** – List Directory Contents  
Displays the files and directories in the current or specified directory.

```bash
ls            # Lists all files and directories
ls -l         # Lists with detailed information (permissions, size, etc.)
ls -a         # Includes hidden files (those starting with .)
```
---

### 2. **`cd`** – Change Directory  
Changes the current working directory to the specified path.

```bash
cd /home/user/Documents    # Navigates to Documents folder
cd ..                      # Moves up one directory level
cd ~                       # Moves to the home directory
```
---

### 3. **`pwd`** – Print Working Directory  
Prints the absolute path of the current working directory.

```bash
pwd   # Displays the full path of your current location
```

---

### 4. **`cp`** – Copy Files or Directories  
Copies files or directories from one location to another.

```bash
cp file1.txt /path/to/destination/         # Copies a file
cp -r folder/ /path/to/destination/        # Copies a directory recursively
```

---

### 5. **`mv`** – Move or Rename Files/Directories  
Moves files or directories to a new location or renames them.

```bash
mv oldname.txt newname.txt                 # Renames a file
mv file.txt /path/to/destination/          # Moves a file
```

---

### 6. **`rm`** – Remove Files or Directories  
Deletes files or directories.

```bash
rm file.txt            # Deletes a file
rm -r folder/          # Deletes a directory and its contents recursively
rm -i file.txt         # Asks for confirmation before deletion
```
**⚠️ Warning:** Be careful with `rm -r`, as it deletes everything inside a directory!

---

### 7. **`echo`** – Print Text to Terminal or Write to a File  
Displays a line of text or writes output to a file.

```bash
echo "Hello, World!"                     # Prints text to the terminal
echo "Hello" > file.txt                  # Writes text to a file (overwrites)
echo "Append this" >> file.txt           # Appends text to a file
```

---

### 8. **`cat`** – Concatenate and Display File Content  
Displays the content of a file or combines multiple files into one.

```bash
cat file.txt                          # Displays the content of a file
cat file1.txt file2.txt > merged.txt  # Combines files into one
```

---

### 9. **`grep`** – Search for Patterns in Files  
Searches for specific text patterns within files.

```bash
grep "keyword" file.txt                # Searches for 'keyword' in a file
grep -i "keyword" file.txt             # Case-insensitive search
grep -r "keyword" /path/to/directory   # Searches recursively in a directory
```

---

### 10. **`chmod`** – Change File Permissions  
Modifies the access permissions of a file or directory.

```bash
chmod 755 script.sh                   # Assigns read, write, and execute permissions to owner; read & execute to others
chmod +x script.sh                    # Adds execute permission to the file
chmod -r file.txt                     # Removes read permission
```

**Common Modes:**
- `777` – Full permissions for everyone.
- `755` – Owner can read, write, and execute; others can only read and execute.
- `644` – Owner can read and write; others can only read.

---
