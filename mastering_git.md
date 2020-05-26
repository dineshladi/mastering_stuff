Grab all the changes in the working directory and store them away. One caveat is that it will leave behind any untracked files. Use `-u` flag to include untracked files as well. 

```bash
git stash -u 
```

View git history in a pretty format with few flags. 

```bash
git log --oneline --decorate --graph --all -30
```

We can configure alias in Git to minimize typing of verbose commands. `sla` is the alias for the below command. 

```
git config --global alias.sla 'log --oneline --decorate --graph --all'
git sla
```

Printing Git log in a pretty format. `%h` is abbreviated commit hash, `%an` is author name, `%ar` is commit authored on date and `%s` is commit subject. 

```bash
git log --pretty=format:'%h - %an [%ar] %s'
```

Search git logs by commit message. `-i` is case insensitive. `-E` is extended regex.  

```bash
git log --grep -E -i regex_string
```

View file specific Git Log. 

```bash
git log --oneline -- file_name
```

See the most recent commit that modified a given line, for every line in the file. 

```bash
git blame file_name
```

View difference of changes introduced in the commit introduced. 

```bash
git show hash_code
```

Appending a change to previous commit when you forget to add something. Git creates a new commit with the last commit message 

```bash
git add forgotten_file
git commit --amend -no-edit 
```

Remove a file from staging. Un-stage 
```bash
git reset file
```

Clean up the working git directory. Remove all the files that are not committed. Be careful while using the following command. 

```bash
git checkout .
```

Undo a commit. It will take back to the state before the commit 
```bash
git reset --soft HEAD^
```
Add different parts of the file to different commits. A file can be both in untracked and staging. Git will let you to review each group of changed lines individually and choose whether or not to stage them. 

```bash
git add --patch
```

Copy commits from one branch to another. Sometimes we have made a commit on the wrong brach. `cherry-pick` allows you to copy commits onto a different branch. 

```bash
git diff origin/master..master

git checkout <target_branch>

git cherry-pick origin/master..master

## Reset the master branch to remove commits that are created in the correct branch

git checkout master
git reset --hard origin/master
```




