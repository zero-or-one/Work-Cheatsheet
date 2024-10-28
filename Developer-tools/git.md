# Git 

## Definition
Git is a distributed version control system used to track changes in source code during software development. It allows multiple developers to work on a project simultaneously.

## Installation
Follow the instructions on the [official Git website](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

## Basic Commands

### 1. Initialize a Repository
```sh
git init
```
Initializes a new Git repository in the current directory.

### 2. Clone a Repository
```sh
git clone <repository_url>
```
Clones an existing repository from a remote server.

### 3. Check Repository Status
```sh
git status
```
Displays the state of the working directory and staging area.

### 4. Add Changes to Staging Area
```sh
git add <file_name>
```
Adds changes in the specified file to the staging area. Use `git add .` to stage all changes.

### 5. Commit Changes
```sh
git commit -m "Commit message"
```
Records changes to the repository with a descriptive message.

### 6. Push Changes to Remote Repository
```sh
git push origin <branch_name>
```
Uploads local branch commits to the remote repository.

### 7. Pull Changes from Remote Repository
```sh
git pull origin <branch_name>
```
Fetches and merges changes from the remote repository to the local branch.

### 8. Create a New Branch
```sh
git branch <new_branch_name>
```
Creates a new branch.

### 9. Switch to a Branch
```sh
git checkout <branch_name>
```
Switches to the specified branch.

### 10. Merge Branches
```sh
git merge <branch_name>
```
Merges the specified branch into the current branch.

### 11. Connect directory to a repo
```sh
git remote add origin <repository-url>
```
Veryfy thr remote
```sh
git remote -v
```