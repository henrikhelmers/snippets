# Homebrew


## Cleanup
```
brew cleanup --prune all (or days)
```


## Dependency tree
```
brew deps --tree --installed
```


## Show leaf nodes
```
brew leaves | xargs brew deps --installed --for-each | sed "s/^.*:/$(tput setaf 4)&$(tput sgr0)/"
```