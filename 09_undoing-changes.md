# Undoing Changes

# Git Reset

## Case 1 : Undo staged changes

1. Unstage a Specific File: 
      -  To unstage a specific file, keeping your changes in the working directory 
      - `git reset <file-name>`
    
2. Unstage All Files: To unstage all files, keeping changes in the working directory
      - This will remove all files from the staging area, but keep your changes in the working directory.
      - `git reset`
        
### Example
staged file --> not staged

![image](https://github.com/user-attachments/assets/1995d975-9d3f-4bbb-a2f2-616cebe304e5)

## Case 2 : Undo commited changes (for one commit)

1. Reset to the Previous Commit:
    - To undo the last commit while keeping changes in the working directory (useful if you want to edit or re-commit)
    - This command moves the current branch pointer back by one commit.
    - The changes from the undone commit will be left in your working directory and staging area.
    - `git reset HEAD~1`

### Example

 ![image](https://github.com/user-attachments/assets/e7ca1042-ec6a-4fdd-a05c-8a4617e6f6f3)

- To view all the commits: `git log`

  ![image](https://github.com/user-attachments/assets/48a2b766-303c-4306-97b3-8921eb92df1c)

## Case 3 : Undo Committed Changes (for many commits)

1. Reset to a Specific Commit:
    -  To undo commits up to a specific commit, keeping changes in the working directory and staging area
    -  This command will move the branch pointer to the specified commit and keep your changes.
    - `git reset <commit-hash>`
      
### Example

   ![image](https://github.com/user-attachments/assets/e695515e-171c-44ab-972a-d575bf28be6c)

2. Reset to a Specific Commit and Discard Changes:
    - To reset to a specific commit and discard all changes (both staged and working directory)
    - This command will remove all changes after the specified commit, including those in the working directory.
    - `git reset -- hard <commit-hash>`
      
### Example

![image](https://github.com/user-attachments/assets/038771e1-7416-4456-8832-9c77d948a327)


# Git Revert

- Undo a Commit Without Losing History
- git revert creates a new commit that undoes the changes made by a previous commit.
- Unlike git reset, it preserves the commit history, making it ideal for collaborative workflows
- `git revert <commit-hash>`
