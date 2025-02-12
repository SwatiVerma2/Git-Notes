# Merging Code

## First way - Using command

- To compare commits, branches, files & more): `git diff <branch-name>` 
- To merge two branches: `git merge <branch-name>`  

## Second -  creating a PR on Github

- Merging code via a Pull Request (PR) on GitHub is a collaborative way to integrate changes from one branch into another. 
- Pull Requests not only merge code but also allow for code review, discussion, and approval workflows. 

###  How to create a Pull Request 

- If you want to merge the code of your branch with the main branch, create a pull request.
  
- Click on `Compare and pull request` 

![image](https://github.com/user-attachments/assets/4c760e7a-71fe-4a23-ba64-ab664ba495fe)

- Create pull request 

![image](https://github.com/user-attachments/assets/aa759b40-1df9-4d2a-94e4-e1a3f66e55bc)

- Merge pull request

![image](https://github.com/user-attachments/assets/de487e04-95fd-4301-aa35-b07b5c5af48d)

- Confirm merge
 
![image](https://github.com/user-attachments/assets/145f5fcb-ca8d-451e-9eb4-8320d3346d16)

- PR is closed now. You can see the same changes on both the branches, fil2.txt has been added to main branch.
  
  ![image](https://github.com/user-attachments/assets/8bb18af0-b293-4e2b-83c7-3359691d6342)

- The changes are merged on github and not on your local system. To get remote changes on your local system use `pull` command.
- The git pull command is used to fetch and merge changes from a remote repository into your local repository.
- `git pull origin main`

![image](https://github.com/user-attachments/assets/9e6437f3-b439-40d4-bab4-c014b1da1f46)

# Git Merge VS Git rebase

## Git Merge

- git merge combines two branches by creating a new "merge commit." It maintains the full history of both branches.

### Example: Merging feature into main

`git checkout main`

`git merge feature`

### Result

![image](https://github.com/user-attachments/assets/7d775146-4832-4b3e-a834-c78746ef487f)

- A merge commit (M) is created to join the branches.
- The history remains non-linear (branches remain visible).

Pros of Merge:

✅ Preserves history (useful for tracking changes).

✅ Safer for shared branches (used in team workflows).

✅ Easy to undo with git revert.

Cons of Merge:

❌ Can create messy history with too many merge commits.

❌ Harder to follow when multiple merges occur.


## Git Rebase

- Rewrites History
- git rebase moves commits from one branch on top of another, rewriting history.

### Example: Rebasing feature onto main

`git checkout feature`

`git rebase main`

### Result

![image](https://github.com/user-attachments/assets/9711fc0a-6684-420c-98c9-51e663fae56e)

- Instead of a merge commit, D and E are rebased onto main.
- No merge commit is created.
- The history becomes linear and clean.

Pros of Rebase:

✅ Cleaner history (avoids unnecessary merge commits).

✅ Easier to understand (history looks like a straight line).

✅ Works well for feature branches before merging.

Cons of Rebase:

❌ Rewrites history (dangerous on shared branches).

❌ Can be complicated if conflicts occur in multiple commits.

❌ Harder to undo (git reflog is needed to recover lost commits).

