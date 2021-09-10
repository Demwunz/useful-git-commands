# Useful Git commands
A collection of useful git commands, because I'm lazy and can't be bothered to remember off by heart


### delete all local branches that have been merged into master
scenario: free up space on your machine. delete anything that's been merged, no need to have it any more.
```sh
git branch --merged master | grep -v "\* master" | xargs -n 1 git branch -d
```

### amend a commit to the current time
scenario: you worked on something at 2am on a Saturday morning. You don't want your colleagues to think you're a madman. Change it before standup on Monday morning.
```sh
git commit --amend --date="now"
```

### add empty git commit without adding files
scenario: You just need to force git to accept a commit without editing files. Useful for CI
```sh
git commit --allow-empty -m "This will trigger a build"
```

### add files without a commit message (opposite of previous command)
scenario: You just need to push some files, but there isn't any significant thing to say e.g removeing console.log commands
```sh
git commit --allow-empty-message -m ""
```

### commit again, don't change anything, but get a new hash
scenario: useful when you need to kick off another build 
```sh
git commit --amend --no-edit -m "nothing changed. need to trigger something"
```

### add hunks of code instead of entire files
scenario: you have made a whole bunch of changes and they all deserve to be in seperate commits
```sh
git add -p
```

### reset your branch to a commit, but keep the changes
scenario: you made a bunch of changes, you have some messed up history, you want to organise your shit
```sh
git reset --soft <commit>
```

### revert your branch to a previous commit, without resetting the branch
scenario: you commit a bunch of stuff, pushed to github, but now you need to back out the changes, and preserve git history
```sh
git revert -m 1 <commit id>
```
