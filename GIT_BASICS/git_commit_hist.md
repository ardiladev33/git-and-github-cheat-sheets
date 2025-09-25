# 5. [The commit history](../README.md)

Viewing a project's commit history is essential for understanding how a codebase has evolved. It's not just a simple log; it’s a detailed narrative that shows who changed what, when, and most importantly, why. This visibility is crucial for debugging issues, tracking down the introduction of a bug, or simply getting context on a specific feature. In short, a clean commit history is the backbone of any well-managed and collaborative project.

## 5.1 Viewing the Commit History

```
git log
```

Use the -p or --patch option to see the actual changes (the patch output) introduced in each commit. You can also limit the number of entries displayed by using a flag like -2 to show just the last two commits:

```
git log -p -2
```

if you want to see some abbreviated stats for each commit, you can use the --stat option:

```
git log --stat
```

For more control over your log's output, use the --pretty option. It has several values like short, full, and oneline—the latter of which is especially useful for a clean, one-line summary of each commit:

```
git log --pretty=oneline
```

The format option for git log gives you complete control over the output, which is invaluable for scripting and automation. Since you define the format yourself, it’s guaranteed to be stable and won’t break with new versions of Git:

```
git log --pretty=format:"%h - %an, %ar : %s"
```

To get a visual representation of your project’s history, combine the --graph option with a simple format like --oneline. This adds a clear ASCII graph to your log, making it easy to see your branching and merging history:

```
git log --pretty=format:"%h %s" --graph
```

## 5.2 Limiting log output

For example, this command gets the list of commits made in the last two weeks:

```
git log --since=2.weeks
```

The -S option, colloquially known as Git's "pickaxe," is a powerful log filter that finds commits where a specific string was either added or removed. This is an invaluable tool for tracking down when a particular function or variable was first introduced:

```
git log -S function_name
```

Another powerful way to filter your log is by providing a specific file or directory path. This will show you only the commits that affected that location; just be sure to add a double-dash (--) before the path to separate it from your other options:

```
git log -- path/to/file
```

To pinpoint commits that meet multiple, specific criteria, you can combine a series of git log filters. For example, you can search for commits from a specific author and date range that only modified certain files while ignoring all merge commits:

```
git log --pretty="%h - %s" --author='Junio C Hamano' --since="2008-10-01" \
--before="2008-11-01" --no-merges -- t/
```
