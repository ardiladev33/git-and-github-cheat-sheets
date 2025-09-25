# 8. [Tagging](../README.md)

Creating a tag in Git is like placing a permanent bookmark on a specific point in your project's history. It's an essential practice for marking significant milestones, such as a new version release or a key bug fix. Tags are lightweight, immutable references that make it easy to find and revert to a particular state without having to remember a long commit hash. Ultimately, they provide a clear, human-readable map of your project's most important moments.

## 8.1 Listing your tags

Listing the existing tags in Git is straightforward. Just type git tag (with optional -l or --list):

```
git tag
```

When a repository has hundreds of tags, you can easily find what you’re looking for by searching with a pattern. For example, to view all tags from a specific version series, you can simply run:

```
git tag -l "v1.8.5*"
```

## 8.2 Creating tags

Annotated tags:

```
git tag -a v1.4 -m "<message>"
```

You can see the tag data along with the commit that was tagged by using the git show command:

```
git show v1.4
```

## 8.3 Lightweight tags

Another way to tag commits is with a lightweight tag. This is basically the commit checksum stored in a file — no other information is kept. To create a lightweight tag, don’t supply any of the -a, -s, or -m options, just provide a tag name:

```
git tag v1.4-lw
```

This time, if you run git show on the tag, you don’t see the extra tag information. The command just shows the commit:

```
git show v1.4-lw
```

## 8.4 Tagging later

```
git tag -a v1.2 <commit_hash>
```

## 8.5 Sharing tags

Unlike branches, git push doesn't transfer tags to the remote by default. You must explicitly push them, which is done just like sharing a remote branch: git push origin {tag_name}

```
git push origin <tag_name>
```

Instead of pushing tags one by one, use the --tags option with git push. This simple command transfers all of your local tags to the remote at once:

```
git push origin --tags
```

## 8.6 Deleting tags

To delete a tag on your local repository, you can use git tag -d {tagname}. For example, we could remove our lightweight tag above as follows:

```
git tag -d <tag_name>
```

Note that this does not remove the tag from any remote servers. There are two common variations for deleting a tag from a remote server.

The first variation is:

```
git push <remote> :refs/tags/<tagname>
```

The second (and more intuitive) way to delete a remote tag is with:

```
git push origin --delete <tagname>
```

## 8.7 Checking out tags

You can use git checkout {tag} to inspect the files at a specific tagged version. Just be aware this puts you in a "detached HEAD" state, where any new commits could be easily lost since they won’t belong to a branch:

```
git checkout <tag_name>
```

Committing in a detached HEAD state is dangerous—your new work won't belong to any branch and can be easily lost. So, if you're fixing an old bug, always create a new branch first to ensure your changes are safe:

```
git checkout -b <branch_name> <tag_name>
```
