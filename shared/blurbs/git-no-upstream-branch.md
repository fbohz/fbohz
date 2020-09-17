**Title Tag**: Git Fixes: The Current Branch Has No Upstream Branch

**Meta Description**: The Current Branch Has No Upstream Branch. Have you seen this error in Git? We'll show you what it is and how to fix it. Learn Git with CareerKarma.

**Slug**: /git-no-upstream-branch/

**Target Keywords**: HTML Forms, Action Attribute.

**Author**: Felipe Bohorquez

**Twitter Message**: The Current Branch Has No Upstream Branch. Have you seen this error in Git? We'll show you what it is and how to fix it. Learn #Git with #CareerKarma.

**Word-Range**: 500 words

**STATUS**: Done

---

# Git Fixes: The Current Branch Has No Upstream Branch

It might happen that you are working on your regular day-to-day coding. You create a new branch, make some commits and then after doing `git push` you get this error:

```bash
fatal: The current branch <branchname> has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin <branchname>
```

This happens because of your newly created branch. Your Git is not configured to create that same branch on remote. So you are creating that branch only on your local. In order to fix this we need to add more options to our git push command.

## Ways to go about solving this issue

There are many ways to solve this issue. The first of them would be to just follow the instructions above. 

`git push --set-upstream origin master`

We caution you to **not use this command**, why? Because you don't need set up an upstream. If you set upstream this way you could have weird and unexpected consequences in your repository. Because of unexpected consequences this option has been deprecated.

There are other ways and as exemplified above we will need to add more options to `git push`.

`git push -u origin master`

This will automatically create the branch with the **same name** of your local on remote. The `-u` creates that branch on the remote repo.  If you ever get an error while doing this command just add the `--all` flag at the end: `git push -u origin --all`. 

**Note**: You might be tempted to omit `-u` and just do `git push origin <branch-name>`. If you don't add this flag when you do `git pull` at some point it will not work as expected and Git will give you some additional errors. So do stick to adding the `-u`


## Configuring Git to allow using `git push` alone

If you still want to use git push without having this error, you'll need to configure Git to always create a remote branch whenever you create a new local branch. We do this with the following command:

`git config --global push.default current`

With this fix you are good to go to use `git push` without seeing this error again! 

## Conclusion

Whenever we work on new branches, most of us have seen this error. We could either configure git to always push to remote as we create the branch or just make that decision ourselves by adding the `-u` flag to our `git push` command. 