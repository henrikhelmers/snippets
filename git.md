# Git


## Cherry pick range of commits
Without `^` the starting commit will be omitted.
`git cherry-pick START^..END`


## Make Nova the default editor
```
git config --global core.editor "nova --wait"
git config --global mergetool.nova.cmd "nova --wait \$MERGED"
git config --global mergetool.nova.trustExitCode true 
git config --global merge.tool nova
```

## Branch by commit date
`git branch --sort=committerdate | tail`