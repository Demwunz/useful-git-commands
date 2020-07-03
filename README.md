# useful-git-commands
A collection of useful git commands


### delete all local branches that have been merged into master
```sh
git branch --merged master | grep -v "\* master" | xargs -n 1 git branch -
```

### amend a commit to the current time
```sh
git commit --amend --date="now"
```

### add empty git commit without adding files
```sh
git commit --allow-empty -m "This will trigger a build"
```
