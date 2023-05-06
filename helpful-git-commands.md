# Doc: Git - Helpful commands that got me out of a jam.

## Update git remote URL
- Run to see the current remote.
- Update remote URL with set-url.
```
git remote -v
git remote set-url origin new_git_url
```
<br>

## Unstaging a Git add (Git v.2.23+) 
Older Git use git reset, see below.
```
git restore --staged fileName.html
```

## Delete any local changes to a file. 
** This undo any modifications to a file since the last commit. This cannot be undone! **
```
git restore fileName.html
```

<br>

## Unstaging a Git add (reset) 
Use ```git reset``` to unstage/exclude a file( or a directory)

```
# All
git reset .

# File
git reset -- file_name_or_path

# Directory
git reset -- directory_name_or_path
```

<br>

## Adding additional entries to .gitignore
- Add the entires which needs to be removed in .gitignore
- Unstage the entries. This does not delete it from working directory
```
# All
git rm -r --cached .

# File
git rm -r --cached file_name_or_path

# Directory
git rm -r --cached directory_name_or_path
```

<br>

## Renaming a Branch
1. Checkout to the branch of choice
2. Rename a branch locally.
3. Push the new branch to remote repo.
4. Delete the branch with old name from remote repo.
```
git checkout branch_name
git branch -m new_branch_name
```

<br>

## Tranfering to a new machine
1. Copy files from ~/.ssh
- id_rsa
- id_rsa.pub
- known_hosts (optional)
2. In your new machine put these files in your ~/.ssh
3. terminal 
```
sudo chmod 400 ~/.ssh/id_rsa
```

<br>

## Fixed comment in the previous commit
```
git commit --amend -m 'Fixed comment'
```
