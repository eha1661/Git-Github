# Git Clean

## Theory

The `git clean` command operates on untracked files. Untracked files are files that have been created within your repo's working directory but have not yet been added to the repository's tracking index using the git add command. `1`

## Hands-on `1`

``` sh
mkdir git_clean_test
cd git_clean_test/
git init .
echo "tracked" > ./tracked_file
git add ./tracked_file
echo "untracked" > ./untracked_file
mkdir ./untracked_dir && touch ./untracked_dir/file
```

Executing the default `git clean` command may produce a fatal error at this point.

It has many options:

* `-n, --dry-run`
* `-d` so that clean will recurse into untracked directories into untracked directories (safety mechanism)
* `-f, --force` The force option initiates the actual deletion of untracked files
* `-X` Remove only files ignored by Git
* `-i, --interactive`

Check help for more options

``` sh
$ git clean -n
Would remove tracked_file
```

It doens't take consideration the directories, so we use `-d`

``` sh
$ git clean -dn
Would remove tracked_file
Would remove untracked_dir/
```

``` sh
$ git clean -f 
Removing untracked_file
```

``` sh
$ git clean -df
Removing untracked_dir/
```

## Resources

* `1`[Bitbucket - Git Clean](https://www.atlassian.com/git/tutorials/undoing-changes/git-clean)