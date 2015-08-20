
# A quick Git reference

## Setup Git

Set Up Git: https://help.github.com/articles/set-up-git/

## Git gibberish 

| Keyword | Description |
|-------|-------------|
| `Working directory` | Actual files and on-going changes on current directory |
| `Index` \| `Staging area` | Snapshot changes set aside to be commited |
| `SHA-1`             | Unique identifier repesenting history and information |
| `blob`              | Represents a file  |
| `tree`              | Represents a directory of files |
| `Commit`            | Represents a tree as recorded in a point in time  |
| `HEAD`              | Represents the latest commit in current branch  |
| `Tag`               | Represents a specific commit used for marking important points in hisotry |


## Getting started

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git init`    |             | Make current directory a git repository |
| `git clone`   | `<giturl>`  | Clone remote repository into current directory |
| `git checkout`| `<sha-1>`  | Switch to branch, or commit |
| `git submodule` | `update --remote` | Pull submodules from remote repo |

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git status`  | `-s`        | Show the working tree status, with `--short` format |
| `git log`     | `--oneline` | Show commit logs, with `--oneline` format |
| `git ls-files`|             | Show information about files in the index and the working tree |

## Diff

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git diff`  |             | Compare **`working directory`** and **`index`** |
|             | `–-cached`  | Compare **`index`** and **`latest commit`** |
|             | `HEAD`      | Compare **`latest commit`** and **`working directory`** |
|             | `--stat`    | Optional short format |
|             | `<commit> <commit> | <branch> <branch>` | 2 points in time to compare |
|             | `<path> | <file>` | Make output relative to `<path>` or limit to `<file>` |

#### Diff examples:

```shell
## compare changes made to README.md between working tree (default) and latest commit (HEAD)
$ git diff --stat HEAD ./path/README.md

## compare changes made to README.md between 2 points in time (e.g. 2 commits)
$ git diff --stat a649900 24bdd58 ./path/README.md
```

## Commit

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git add`         | `<file> | <path>`   |  Add files to staging area  |
| `git commit`      | `-m "<title>" -m "<body>"`  |  Commit with message (includes "added" files only) |
| `git rm`          | `<file> | <path>`   |  Remove files from the working tree and from the index |
|                   | `-f`                |  Force deletion of files from disk |

## Push

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git push`         | `origin <branchname>`  |  Push branch to remote server  |
| `git push`         | `origin <tagname>`     |  Push tag  |
| `git push`         | `origin --tags`        |  Push all tags  |

## Branch

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git branch`        |                   | List branches |
| `git branch`        | `<branchname>`    | Create new branch |
| `git merge`         | `<branchname>`    | Merge changes from `<branchname>` to current tree |
| `git branch`        | `-d <branchname>` | `--delete` branch |
| `git push`          | `--d origin <branchname>` | `--delete` remote branch |

## Tag

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git tag`           |                   | List available tags |
| `git tag`           | `<v1.0.0>`        | Create tag, from latest commit, lightweight |
| `git tag`           | `-a <v1.0.0> -m "<msg>"` | Create tag, with `--annotate`, from latest commit |
| `git tag`           | `-a <v1.0.0> -m "<msg>" <SHA-1>` | Create tag, with `--annotate`, from specific commit |
| `git tag`           | `-d  <v1.1.0>`    | `--delete` tag |
| `git show`          | `<v1.0.0>`        | Show tag data and message |
| `git checkout`      | `<v1.0.0>`        | Switch to specific point tag (not editable) |


