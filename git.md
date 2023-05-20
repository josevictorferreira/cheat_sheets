
# Git Useful commands

## Squash

To force squash of all commits on a single branch into a single one use the following commands:
```
git checkout yourBranch
git reset $(git merge-base main $(git branch --show-current))
git add -A
git commit -m "one commit on yourBranch"
```

OR:

```bash
git switch yourBranch
git reset --soft $(git merge-base main HEAD)
git commit -m "one commit on yourBranch"
```
