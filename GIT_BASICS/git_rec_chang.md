# 4. [Recording changes to the repository](../README.md)

At its core, recording changes in a Git repository is about more than just saving your work. Each commit creates a permanent snapshot, giving us the power to precisely track and revert to any point in the project's history. This discipline is what allows for seamless collaboration and builds a clear, documented timeline of a project's evolution.

## 4.1 Checking the status of your files

```
git status
```

## 4.2 Tracking new files

Review sections 3.3 and 3.4 of [Getting started with a Git repository](./git_init_repo.md)

## 4.3 Short status

```
git status -s
```

## 4.4 Ignoring files

Every project has files—like build artifacts, logs, or editor settings—that should not be tracked by Git. These files often clutter your status output and can be accidentally committed. To manage this, you can create a .gitignore file at the root of your project. Inside, you simply list the patterns for files and directories you want Git to completely disregard.

Example:

```
echo node_modules/ > .gitignore
```

## 4.5 Viewing your staged and unstaged changes

```
git diff
```

If you want to review the changes you've staged for your next commit, you can use the git diff --staged command. This command is a powerful way to double-check your work, as it shows you exactly what's queued up by comparing your staged changes directly against your last commit:

```
git diff --staged
```

git diff --cached to see what you’ve staged so far (--staged and --cached are synonyms):

```
git diff --cached
```

## 4.6 Committing your changes

To make a commit via the integrated text editor:

```
git commit
```

Alternatively, you can type your commit message inline with the commit command by specifying it after a -m flag, like this:

```
git commit -m "<message>"
```

## 4.7 Skipping the staging area

For a quick way to commit your changes without manually staging each file, Git offers a useful shortcut. By adding the -a flag to the git commit command, Git will automatically stage all files that it's already tracking before performing the commit. This lets you completely bypass the git add step, which is a great way to streamline your workflow for minor updates:

```
git commit -am '<message>'
```

## 4.8 Removing files

When you simply delete a file from your working directory, Git immediately recognizes the change. The removed file will then be listed under the Changes not staged for commit section of your git status output, indicating that the deletion has been detected but not yet staged for your next commit:

```
git rm <file_name>.<file_extension>
git status
```

Another useful thing you may want to do is to keep the file in your working tree but remove it from your staging area:

```
git rm --cached <file_name>
```

You can pass files, directories, and file-glob patterns to the git rm command. That means you can do things such as:

```
git rm log/\*.log
```

You'll notice the backslash in front of the asterisk. This is a crucial detail because the wildcard is a character that gets expanded by your shell before Git even sees it. By using a backslash, you're essentially telling your shell to ignore the wildcard, passing it directly to Git so Git can handle the file expansion properly. The command then removes all files with a .log extension in the log/ directory:

```
git rm \*~
```

## 4.9 Rename files

Thus it’s a bit confusing that Git has a mv command. If you want to rename a file in Git, you can run something like:

```
git mv <file_from> <file_to>
```
