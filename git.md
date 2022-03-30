# git 

## Remove all branches but current
```
git branch | grep -v '*' | xargs git branch -D
```

## Undo git commit --amend

```
# Move the current head so that it's pointing at the old commit
# Leave the index intact for redoing the commit.
# HEAD@{1} gives you "the commit that HEAD pointed at before 
# it was moved to where it currently points at". Note that this is
# different from HEAD~1, which gives you "the commit that is the
# parent node of the commit that HEAD is currently pointing to."
git reset --soft HEAD@{1}

# commit the current tree using the commit details of the previous
# HEAD commit. (Note that HEAD@{1} is pointing somewhere different from the
# previous command. It's now pointing at the erroneously amended commit.)
git commit -C HEAD@{1}
```
[source](https://stackoverflow.com/questions/1459150/how-to-undo-git-commit-amend-done-instead-of-git-commit)

## Fetch PR
To fetch a remote PR into your local repo,

```
git fetch origin pull/$ID/head:$BRANCHNAME
```
where $ID is the pull request id and $BRANCHNAME is the name of the new branch that you want to create. Once you have created the branch, then simply

```
git checkout $BRANCHNAME
```
[sourcee](https://stackoverflow.com/questions/27567846/how-can-i-check-out-a-github-pull-request-with-git)
