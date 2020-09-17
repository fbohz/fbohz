**Title Tag**: Git Detached HEAD

**Meta Description**: Do you know how to detach the HEAD (not literally) and what it means in Git? Learn about this mysterious Git state with CareerKarma.

**Slug**: /git-detached-head/

**Target Keywords**: Git, Detached Head

**Author**: Felipe Bohorquez

**Twitter Message**: Do you know how to detach the HEAD (not literally) and what it means in #Git? Learn about this mysterious Git state with #CareerKarma.

**Word-Range**: 750 words

**STATUS**: Done

---

# Git Detached HEAD

While often you might not encounter the problem of a detached HEAD, it is important to know about so that you can avoid it. And as a recommendation **do not commit on a detached HEAD** because it has no purpose at all.

## A Reminder

In order to understand what the HEAD is, let's do a refresher on Git's underlying tree-like structure.

1. **The Working Directory**: Or working tree. It refers to your local directory and `git status` will give you the state of your working directory.
2. **HEAD**: It is just your current branch last commit snapshot. If you where to switch branches with `git checkout` then the HEAD will change to the last commit on the branch.
3. **Index**: Or staging area, so when you `git add` files to commit it adds them to this index.

## Understanding an attached HEAD

Now that we understand that HEAD is just the latest commit on the current branch you are on. By doing `git status` it will tell your branch e.g. `On branch master` and by doing `git log` it will tell your commit history with information such as:

```bash
commit 38373004b8f651b58cea64cd629e1e2c18c164a0 (HEAD -> master, origin/master, origin/HEAD)
Author: Felipe <email>
Date:   Wed Sep 29 22:57:59 2020 -0500
```

Then if we were to change change our branch to let's say development branch with `git checkout development` then the HEAD will move to the last commit. So in all this normal cases of Git flow the head is following us as it is supposed to be, attached.

## Detaching the HEAD

There are a couple of ways we can detach our HEAD.

- Using the `git checkout --detach` command.
- Checkout out to a commit hash. E.g. using commit from above `git checkout 38373004b8f651b58cea64cd629e1e2c18c164a0`
- By adding `^0` on any given branch. E.g. `git checkout master^0`.

I'm not sure whether you'd like intentionally detach HEAD. So the most common case is that by mistake you will try to checkout to a branch and used a commit hash instead of the branch name.

So what happens? You might get a warning similar to this:

```bash

$ git checkout 38373004b8f651b58cea64cd629e1e2c18c164a0
Note: checking out '38373004b8f651b58cea64cd629e1e2c18c164a0'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at 3837300...
```

If you do `git status` even though you made changes it will say something like

```bash
HEAD detached at ac63806
nothing to commit, working tree clean
```

It will be like you are frozen in time and everything you do is lost, or merely not going anywhere. Why? Well because the HEAD is not pointing to anything. You might find this useful if you want to explore a previous state of your repository without any worries of breaking things.

## Re-Attaching the HEAD

You must understand that **your other branches are not affected by getting into a detached state**. Now the best way to re-attach the HEAD is to well create a new branch. We can do it as simple as `git checkout -b <branch-name>`.

Now what if we didn't realized we were without a HEAD and started making changes? Well here we will need to create a temporary branch and just merge with the branch we need to commit. For example:

```bash
git checkout -b temp-branch
git checkout master
git merge temp-branch
```

This will commit the changes from your temporary branch into the branch you need them. In this case master.

## Conclusion

Today we learned how to detach our HEAD (not literally) and what to do afterwards. Understanding what the HEAD is in the Git inner workings can help us understand special cases such as a detached HEAD. But do not worry we would not have to worry about living a detached HEAD state, just when you do do have in mind that since your HEAD is loose whatever changes will not be reflected anywhere so make sure you re-attached the HEAD accordingly.
