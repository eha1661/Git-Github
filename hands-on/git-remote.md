# Git Remote

## Theory

The `git remote` command lets you create, view, and delete connections to other repositories
The `git remote` command is essentially an interface for managing a list of remote entries that are stored in the repository's `./.git/config` file.

## Hands-on

#### 1. create an empty github repo `hands-on-git-remote`

#### 2. create a local repo

``` sh
mkdir hands-on-git
cd hands-on-git
```

``` sh
echo "# hands-on-git-remote" >> README.md
git init
git add README.md
git commit -m "first commit"

# -M  Shortcut for --move --force
# -m, --move  Move/rename a branch and the corresponding reflog.
git branch -M main # 
```

#### 3. ceate the connection between the local and remote

``` sh
# git remote add <name> <url>
git remote add origin https://github.com/eha1661/hands-on-git-remote.git
```

``` sh
## Check connections
# List the remote connections
$ git remote
origin
# List the remote connections with urls
$ git remote -v
origin	https://github.com/eha1661/hands-on-git-remote.git (fetch)
origin	https://github.com/eha1661/hands-on-git-remote.git (push)
```

``` sh
# -u, --set-upstream For every branch that is up to date or successfully pushed, add upstream (tracking) reference,

# git push <remote-name> <branch-name>
# git push -u origin main
```

#### 4. manipulate connection to the remote repository

Rename the connection to the remote repository

``` sh
# git remote rename <old-name> <new-name>
git remote rename origin my-remote
```

``` sh
$ git remote
my-remote
```

Remove the connection to the remote repository

``` sh
# git remote rm <name>
git remote rm  my-remote
```

## Notes

## Resources

* `1` [bitbucket - git remote](https://www.atlassian.com/git/tutorials/syncing)