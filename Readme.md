# Complete Git Commands Reference

## 1. Git Configuration

Configure your Git environment with user information and preferences.

```bash
# Set global username
git config --global user.name "Your Name"

# Set global email
git config --global user.email "you@example.com"

# Set default editor (VS Code)
git config --global core.editor code

# View all configurations
git config --list

# Edit global config file
git config --global --edit
```

## 2. Repository Setup

Initialize new repositories or connect to existing ones.

```bash
# Initialize a new repository
git init

# Clone repository from remote
git clone <repository-url>

# Add remote origin
git remote add origin <repository-url>

# View all remotes
git remote -v

# Remove remote origin
git remote remove origin
```

## 3. Basic File Operations & Staging

Track changes and prepare commits with these fundamental commands.

```bash
# Check file status
git status

# Add specific file to staging area
git add <filename>

# Add all files to staging area
git add .
# Alternative: git add --all

# Remove file from staging area
git reset <filename>
# Alternative: git restore --staged <filename>

# Commit staged changes with message
git commit -m "commit message"

# Stage and commit tracked files in one command
git commit -am "commit message"
# Alternative: git commit -a -m "commit message"
```

## 4. Viewing Changes & Differences

Compare different states of your files and repository.

```bash
# Show unstaged changes
git diff

# Show staged changes (what will be committed)
git diff --staged

# Show changes between commits
git diff <commit1> <commit2>

# Show changes in a specific file
git diff <filename>
```

## 5. Branching & Switching

Manage different lines of development in your project.

```bash
# List all branches
git branch

# Create new branch
git branch <branch-name>

# Switch to existing branch
git checkout <branch-name>
# Modern alternative: git switch <branch-name>

# Create and switch to new branch
git checkout -b <branch-name>
# Modern alternative: git switch -c <branch-name>

# Merge branch into current branch
git merge <branch-name>

# Delete branch (safe delete)
git branch -d <branch-name>

# Force delete branch
git branch -D <branch-name>
```

## 6. Remote Operations & Syncing

Synchronize your local repository with remote repositories.

```bash
# Download remote changes without merging
git fetch

# Download and merge remote changes
git pull

# Pull from specific branch
git pull origin <branch-name>

# Push changes to remote
git push

# Push to specific branch
git push origin <branch-name>

# Set upstream branch and push
git push -u origin <branch-name>

# Delete remote branch
git push origin --delete <branch-name>
```

## 7. Commit History & Information

Explore your project's history and get detailed information.

```bash
# View full commit history
git log

# View commit history in one line per commit
git log --oneline

# View branch graph with decorations
git log --graph --oneline --decorate

# Show specific commit details
git show <commit-hash>

# Show who changed each line in a file
git blame <filename>

# Show reference log (HEAD movement history)
git reflog
```

## 8. Undoing Changes & Fixes

Correct mistakes and revert unwanted changes safely.

```bash
# Restore file to last committed state
git restore <filename>

# Remove file from staging area
git restore --staged <filename>

# Undo last commit but keep changes staged
git reset --soft HEAD~1

# Undo last commit and unstage changes (default)
git reset --mixed HEAD~1
# Alternative: git reset HEAD~1

# Undo last commit and discard all changes
git reset --hard HEAD~1

# Create new commit that undoes previous commit
git revert <commit-hash>

# Remove untracked files and directories
git clean -fd
```

## 9. Stashing

Temporarily save work without committing.

```bash
# Save current changes to stash
git stash

# Save changes with descriptive message
git stash save "work in progress on feature X"

# List all stashes
git stash list

# Apply most recent stash and remove it
git stash pop

# Apply specific stash without removing it
git stash apply stash@{n}

# Remove specific stash
git stash drop stash@{n}

# Clear all stashes
git stash clear
```

## 10. Tags & Releases

Mark specific points in your repository's history.

```bash
# List all tags
git tag

# Create lightweight tag
git tag <tag-name>

# Create annotated tag with message
git tag -a <tag-name> -m "tag message"

# Push specific tag to remote
git push origin <tag-name>

# Push all tags to remote
git push --tags

# Delete local tag
git tag -d <tag-name>

# Delete remote tag
git push origin --delete <tag-name>
```

## 11. Advanced Operations

Powerful commands for complex Git operations.

```bash
# Apply specific commit to current branch
git cherry-pick <commit-hash>

# Reapply commits on top of another branch
git rebase <branch-name>

# Interactive rebase for editing commit history
git rebase -i <commit-hash>

# Find commit that introduced a bug using binary search
git bisect start
git bisect bad <commit-hash>
git bisect good <commit-hash>

# Create ZIP archive of repository
git archive --format=zip HEAD > project.zip

# Add submodule to repository
git submodule add <repository-url>

# Update submodules
git submodule update --init --recursive
```

## 12. Git Flow Summary

### Basic Workflow: Untracked → Staged → Committed

```bash
# 1. Check status
git status

# 2. Add files to staging area
git add .

# 3. Commit changes
git commit -m "descriptive message"

# 4. Push to remote
git push origin main
```

### Unstaging Files

```bash
# Remove file from staging area (keep changes)
git restore --staged <filename>

# Remove all files from staging area
git restore --staged .
```

### File States Flow

1. **Untracked** → `git add` → **Staged** → `git commit` → **Committed**
2. **Staged** → `git restore --staged` → **Modified (Unstaged)**
3. **Modified** → `git restore` → **Clean (Last Committed State)**

## Quick Reference Commands

| Command                  | Description              |
| ------------------------ | ------------------------ |
| `git status`             | Check repository status  |
| `git add .`              | Stage all changes        |
| `git commit -m "msg"`    | Commit with message      |
| `git push`               | Push to remote           |
| `git pull`               | Pull from remote         |
| `git log --oneline`      | View commit history      |
| `git branch`             | List branches            |
| `git checkout -b <name>` | Create and switch branch |
| `git merge <branch>`     | Merge branch             |
| `git stash`              | Save work temporarily    |

---

_This reference covers the most commonly used Git commands. For more advanced features, consult the official Git documentation._
