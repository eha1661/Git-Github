# Commit --amend

## Theory

The git commit --amend command is a convenient way to modify the most recent commit. It lets you combine staged changes with the previous commit instead of creating an entirely new commit.

For instance, it allows you to:

* change most recent Git commit message
* changing committed files

## Hands-on

``` sh
mkdir git-commit-amend
cd git-commit-amend/
git checkout -b main
git init 
git checkout -b main
echo "firs line" > README.md
git add .
git commit -m "commit comment to change"
```

``` sh
$ git log --oneline
638586e (HEAD -> main) commit comment to change
```

Change the last commit message to "initial commit"

``` sh
git commit --amend -m "initial commit"
```

``` sh
$ git log --oneline
f55b17e (HEAD -> main) initial commit
```

You forgot to add a documentation file `doc.md`, add the doc file to the same commit.

``` sh
# add doc.md to staging area
echo "doc instruction" > doc.md
git add .
```

``` sh
git commit --amend --no-edit
```

``` sh
$ git log --oneline
0438874 (HEAD -> main) initial commit
```

## Notes

## Resources

* [atlassian `git-commit--amend`](https://www.atlassian.com/git/tutorials/rewriting-history#git-commit--amend)
* [w3schools](https://www.w3schools.com/git/git_amend.asp)
