# git 

## Remove all branches but current
```
git branch | grep -v '*' | xargs git branch -D
```
