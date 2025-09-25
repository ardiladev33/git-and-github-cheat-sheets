# 7. [Working with remotes](../README.md)

At its heart, working with remotes is the essence of collaboration in Git. It provides a single source of truth for your project, a central place where teams can share code and keep their work synchronized. This not only serves as a robust backup of your entire codebase but also streamlines the workflow for a distributed team. Ultimately, it's the critical link that allows a group of developers to build something cohesive and powerful together.

## 7.1 Showing your remotes

```
git remote
```

You can also specify -v, which shows you the URLs that Git has stored for the shortname to be used when reading and writing to that remote:

```
git remote -v
```

## 7.2 Adding remote repositories

We’ve mentioned and given some demonstrations of how the git clone command implicitly adds the origin remote for you. Here’s how to add a new remote explicitly. To add a new remote Git repository as a shortname you can reference easily, run git remote add {shortname} {url}

```
git remote add <remote_name> <url>
```

If you want to get all the information from a remote that you don't yet have in your repository, you can run git fetch {remote_name}:

```
git fetch <remote_name>
```

## 7.3 Fetching and pulling from your remotes

As you just saw, to get data from your remote projects, you can run:

```
git fetch <remote_name>
```

You can use the git pull command to automatically fetch and then merge that remote branch into your current branch:

```
git pull <remote_name>
```

## 7.4 Pushing to your remotes

```
git push <remote_name> <branch_name>
```

## 7.5 Inspecting a remote

If you want to see more information about a particular remote:

```
git remote show <remote_name>
```

## 7.6 Renaming and removing remotes

If you want to rename a remote:

```
git remote rename <old_name> <new_name>
```

If you want to remove a remote for some reason:

```
git remote remove <remote_name>
```
