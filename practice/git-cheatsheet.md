# Git Quick Reference

## Daily Workflow
git pull origin main      # Get latest changes from GitHub
git status                # Check current state
git diff                  # See unstaged changes
git diff --staged         # See staged changes
git add filename          # Stage specific file
git add .                 # Stage everything
git commit -m "message"   # Create snapshot
git push origin main      # Upload to GitHub

## Inspection
git log --oneline         # View commit history (compact)
git log                   # View full commit history
git diff HEAD~1           # Compare to previous commit

## Undo
git restore filename           # Discard unstaged changes
git restore --staged filename  # Unstage a file
