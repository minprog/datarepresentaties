# Exercises: Working with Files and Directories

## Level 1: Basic Commands

1. **Where am I?**  
   - Open a terminal and check your current location using a command.
   - Navigate to your home directory if you are not already there.

2. **List Files and Directories**  
   - Use a command to list all files and directories in your current location.
   - Try listing files including hidden ones.

3. **Create a Directory**  
   - Create a new directory called `my_project`.
   - Move into the `my_project` directory and confirm you are inside it.

## Level 2: File and Directory Operations

4. **Create and Move Files**  
   - Inside `my_project`, create an empty file called `notes.txt`.
   - Use a text editor to add the line `My first project notes` to `notes.txt`.

5. **Copy and Rename**  
   - Copy `notes.txt` to a new file called `backup_notes.txt`.
   - Rename `backup_notes.txt` to `notes_backup.txt`.

6. **Create a Subdirectory and Move Files**  
   - Inside `my_project`, create a new directory called `docs`.
   - Move `notes_backup.txt` into `docs/`.

## Level 3: Advanced Operations

7. **Remove Files and Directories**  
   - Create a new directory called `temp_files` and inside it, create three empty files: `file1.txt`, `file2.txt`, and `file3.txt`.
   - Delete `file2.txt`.
   - Remove the entire `temp_files` directory (be careful!).

8. **Challenge: Organizing a Project**  
   - In `my_project`, create the following directory structure:
     ```
     my_project/
     ├── docs/
     │   ├── notes_backup.txt
     ├── src/
     ├── tests/
     ```
   - Move `notes.txt` into the `docs/` folder.
   - Create a new empty file in `src/` called `main.py`.

9. **Super Challenge: Script Automation**  
   - Write a simple shell script that:
     - Creates a directory named `new_project`.
     - Moves into `new_project`.
     - Creates three subdirectories: `code/`, `data/`, and `results/`.
     - Creates an empty file `README.md` inside `new_project`.
   - Run your script and verify the structure was created correctly.

These exercises build in complexity and reinforce key shell commands for file and directory management. Happy coding!

