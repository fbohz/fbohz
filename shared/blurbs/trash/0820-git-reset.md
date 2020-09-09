**Title Tag**: Git Reset To The Rescue

**Meta Description**: Do you know about when to use git reset? Learn everything about this life-saver git command. Learn Git with CareerKarma.

**Slug**: /git-reset/

**Target Keywords**: Git, Git Reset

**Author**: Felipe Bohorquez

**Twitter Message**: Do you know about when to use git reset? Learn everything about this life-saver #gitcommand Learn #Git with CareerKarma.

**Word-Range**: 750 words

---

# Git Reset To The Rescue

When you are working on a project by yourself or as part of a team, there might be instances when you want to undo a commit. The `git reset` command is one of the tools you want to use in such cases.

## Git's Tracking Trees

Before going to `git reset`, we need to understand about the underlying structure of git. Git manages and tracks files, through a tree-like data structure with nodes and pointers. So there are basically three of these "trees" on your local git repository:

1. **The Working Directory**: Or working tree, and it refers to your local directory and `git status` will give you the state of your working directory.
2. **HEAD**: Is just your current branch last commit snapshot. If you where to switch branches with `git checkout` then the HEAD will change to the last commit on the branch. 
3. **Index**: Or staging area, so when you `git add` files to commit it adds them to this index.

## Git's Workflow

The following examples shows making changes to a file and then adding it to index (staging) using `git add` then checking `git status` to see changes to be committed.

![Screen Shot 2020-08-21 at 6 26 08 PM](https://user-images.githubusercontent.com/15071636/90942548-e22a7e00-e3db-11ea-8a56-72be4425b16d.png)

Now when we do `git commit` it saves as a more permanent snapshot and updates the master and HEAD to that pointer. So if we do `git status` **after** `git commit`, we'll see that all three trees are in the same state (there will be nothing to commit).

![Screen Shot 2020-08-21 at 7 21 11 PM](https://user-images.githubusercontent.com/15071636/90944342-be6b3600-e3e3-11ea-8aeb-5add911cf4b2.png)

**So what's the purpose of `git reset`?**

You might be wondering why all this preamble just to get to git reset. Well `git reset` manipulates these trees in different ways. By default `git reset` will accept a variety of options depending of what you want to do.

## Git Reset Modes

Let's say we committed some changes and files, then to realize we committed them to the wrong branch or our commit is buggy so we want to rewind. Here's where knowing about the git reset modes is useful.

All git reset with mode will update the HEAD pointer. The mode has the following syntax `git reset <mode> <commit-optional>`. Its main modes are:

- `--soft`: Resets HEAD pointer and leaves the index and working directory untouched. So your HEAD will be reset and the other trees still showing the latest changes.
- `--mixed`: **Default** option. Resets the HEAD and index. This basically un-stages all your changes and leaves you before you did `git add`. *Note:* If you do git reset by itself without any options, it will be interpreted as `git reset --mixed`. 
- `--hard`: **Be careful with this one**. Besides resetting HEAD, index, it also resets your working directory. So you could loose code written! This as any changes after current HEAD pointer (last commit) are discarded.

Other modes such as `--merge` and `--keep` can be read in the [official documentation](https://git-scm.com/docs/git-reset).

## Useful `git reset` Tips

**Rewinding a commit**

Often you'll see git reset used in conjunction with HEAD. As you know if we omit the mode it will be interpreted as --mixed. Now if we just type `git reset HEAD` nothing will happen, but if we do `git reset HEAD~1` then our HEAD will now point to its previous commit. 

The following example continues from the previous one. Now we added new text to our sample file. Then we git add and commit. Then after we do `git reset HEAD~1`, all our changes are un-staged. 

![Screen Shot 2020-08-21 at 8 17 54 PM](https://user-images.githubusercontent.com/15071636/90945697-0d1cce00-e3ec-11ea-935a-7f9378d219f0.png)

This is an useful and fast way when we want to undo a commit!

**Un-staging a specific file**

Let's say you added a file to the index with `git add` we can remove that file just by doing:

`git reset HEAD <file-name>`

**I messed up all my code! Can I go back when it was working?**

If you want to throw away all local changes and go back to your previous commit your last resort is `git reset --hard`. Often if you break your code this could be your only option. If you know the commit hash you can do `git reset --hard <commit>` but note this one will also affect any other commits after (if any)!

**Oh shhh this commit was supposed to be in a new branch!**

This often happens, specially when you are starting to work in production. What we need to do is basically create the new branch that has the state of the branch we need to rewind. Then we wil reset the affected branch and then we checkout to the new branch and do the commits there:

```bash
git branch new-branch
git reset HEAD~1 --hard
git checkout new-branch
```

Lifesaver right!

## One Last Word

Be careful when doing `git reset --hard` and also when rewinding to a specific commit, specially in production code and when you are working with other developers. Often `git revert` is the safe way to make this changes. But that is a conversation for another time. Until then! 👋🏼