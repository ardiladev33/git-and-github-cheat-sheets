# 9. [Git Aliases](../README.md)

Aliasing is one of Git’s most powerful yet underutilized features. By creating custom shortcuts for long or complex commands, aliases not only speed up your workflow but also help simplify your command history, making it far more readable. This simple act of personalization reduces the risk of typos and, most importantly, allows you to craft a more efficient and comfortable command-line experience.

## 9.1 Set Git aliases

```
git config --global alias.<alias_name> '<command>'
```

While most Git aliases run subcommands, you can prefix a command with ! to run an external shell command instead. This is invaluable for creating shortcuts to your own scripts or helper tools that interact with a repository:

```
git config --global alias.visual '!gitk'
```
