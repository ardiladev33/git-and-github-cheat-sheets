# 3. [Getting started with a Git repository](../README.md)

A strong start is everything in Git; correctly initializing a new project or cloning an existing one sets the foundation for a clean, traceable history. It's a foundational step that enables precise version control and reliable collaboration from the very beginning. Once you're working, knowing how to add files to the staging area is crucial for curating your commits and bundling only relevant changes together. This control, along with the ability to unstage files to fix any mistakes, ensures your project's commit history remains logical and easy for your team to understand.

## 3.1 Initializing a repository

```
git init
```

## 3.2 Cloning an existing repository

To clone a repository to the current local directory:

```
git clone <github_repository_url>
```

## 3.3 Add files to the staging area

To stage all the files in the current directory, including those in its subdirectories:

```
git add .
```

To stage all files in the current directory and its subdirectories that match the specified extension:

```
git add *.<extension_file>
```

To stage all files within a directory and its subdirectories, using a path relative to the current location:

```
git add ./<dir_name>
```

To stage a specific file using a path relative to the current directory.

```
git add ./<dir_name>/<file_name>.<extension_file>
```

## 3.4 Unstage files

To unstage all files that have been added, located in the current directory and its subdirectories:

### a.

```
git reset .
```

### b.

```
git restore --staged .
```

To unstage a specific file that has been added, using a path relative to the current directory:

### a.

```
git reset ./<dir_name>/<file_name>.<file_extension>
```

### b.

```
git restore --staged ./<dir_name>/<file_name>.<file_extension>
```
