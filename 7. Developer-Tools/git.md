## Definititon
Git is a distributed version control system for tracking changes in source code during software development. It allows multiple developers to work on a project simultaneously.

## Commands

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

### 12. Large File System (LFS)
Helps manage large files in a Git repository efficiently. It works by storing pointers to the large files in the Git repository itself, while storing the actual file contents on a separate server. 

Install Git LFS:
```Bash

git lfs install
```
Create a .gitattributes file in your repository to specify which file types should be tracked by Git LFS. \
For example, to track all files with the .dat extension, you would add the following line to your .gitattributes file:
```
*.dat filter=lfs
```

Once you have configured Git LFS, you can add and commit large files to your repository as usual. 

### 13. Pull Requestion in GitHub (PL)
1. Create a new branch for your changes.
2. Make your changes to the branch.
3. Push your changes to the remote branch on GitHub.
4. On GitHub, navigate to your repository and click on the "Pull requests" tab.
5. Click on the button to "Create pull request".
6. Enter a title and description for your pull request.
7. Click on the "Create pull request" button.
