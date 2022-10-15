# Git cheat sheet

A simple git cheat sheet so you won't have to remember any commands

## Init

#### Create a new local repository
```
git init
```

#### Create a clone of a repository into a new working directory
```
git clone /link/to/repository
```

#### Connect local repository to a remote server
```
git remote add origin <server-address>
```

## Add/Commit

#### Stage one or more files
```
git add <filename>
```

#### Stage all the files in the current working directory
```
git add .
```

#### Commit staged changes to local head
```
git commit -m "Commit message"
```

## Status/logs

#### List the status of all the files in git repository's working directory
```
git status
```

#### List all the commits that have been applied to a git repository
```
git log
```

## Branches

#### Create a branch and switch to it
```
git switch -c <branch-name>
```
Or alternatively
```
git checkout -b
```

#### Switch to a different branch
```
git switch <branch-name>
```
Or alternatively
```
git checkout <branch-name>
```

#### Delete a git branch
```
git branch -d <branch-name>
```
If the branch has unmerged changes but you still want to delete it
```
git branch -D <branch-name>
```

#### Push a branch to a remote repository
```
git push origin -u <branch-name>
```
Alternatively if you want to push all branches
```
git push --all origin
```

