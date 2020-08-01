+++
title = "Git"
date = 2020-05-13T17:49:23+02:00
weight = 2
+++


Industry standard version control.

## Stash

Stash is a good way to save changes before committing them if for example you want to change branches or merge something new into the branch you are working on. Think of `git stash` as a separate storage place to temporarily store your changes.

Store changes in stash

```bash
git stash
```

Retreive latest changes from stash

```bash
git stash pop
```

Retreive specific changes from stash

```bash
git stash pop stash@{index_number}

git stash pop stash@{1}
```

List changes in stash

```bash
git stash list
```

Show the most recent stash

```bash
git stash show -p
```

Stash single file

```bash
git stash -- filename.txt
```


## Multiple Git Remotes

http://caseyscarborough.com/blog/2013/08/25/pushing-to-multiple-remotes-using-git/


## Untrack files added to git based on gitignore

http://www.codeblocq.com/2016/01/Untrack-files-already-added-to-git-repository-based-on-gitignore/