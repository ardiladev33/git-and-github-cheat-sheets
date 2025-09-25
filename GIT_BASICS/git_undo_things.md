# 6. [Undoing things](../README.md)

No software project is perfect, and sometimes you need a way to go back and fix mistakes. Undoing things in Git isn't about hitting an "undo" button; it's about having a full suite of commands that allow you to gracefully correct errors at any stage of your workflow. This crucial ability lets you safely revert commits, unstage files, or even roll back to a previous state without losing your valuable work.

## 6.1 Undoing things (Commit)

If you want to redo that commit, make the additional changes you forgot, stage them, and commit again using the --amend option:

```
git commit --amend
```

## 6.2 Unstaging a staged file

Review sections 3.4 of [Getting started with a Git repository](./git_init_repo.md)

## 6.3 Unmodifying a modified file

To discard modifications made to a file, restoring it to its last committed state:

```
git checkout -- <file_name>
```

## 6.4 Undoing things with git restore

Unstaging a staged file with git restore:

```
git restore --staged <file_name>
```

Unmodifying a Modified File with git restore:

```
git restore <file_name>
```
