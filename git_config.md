# 1. [Global Git configurations](./README.md)

Making a one-off adjustment to your global Git configuration is a simple yet crucial step for professional developers. By setting your username and email once, you establish a clear identity for all future contributions, ensuring accurate authorship across every project you work on. This practice is key to maintaining a clean and professional commit history, which is fundamental for effective collaboration and project accountability. It also eliminates the need to remember these details for each new repository, streamlining your workflow.

## 1.1 View all of your settings

```
git config --list
```

You can view all of your settings and where they are coming from using:

```
git config --list --show-origin
```

## 1.2 Set default branch "main"

```
git config --global init.defaultBranch main
```

To rename the master branch to main:

```
git branch -M master main
```

## 1.3 Set your identity

How to set up your Git username:

```
git config --global user.name "your username"
```

How to set up your Git email (It's recommended that it matches the email associated with your GitHub account):

```
git config --global user.email <your email>
```

## 1.4 Set your editor

You can configure the default text editor that will be used when Git needs you to type in a message. If not configured, Git uses your system’s default editor [1].

If you want to use a different text editor, such as Emacs, you can do the following [1]:

```
git config --global core.editor emacs
```

## 1.5 View or change the global configs

With this command, you can view or modify the global configurations that enable that action:

```
git config --global -e
```

## References

1. **Scott Chacon & Ben Straub** (2025). _Pro Git_. Apress.
