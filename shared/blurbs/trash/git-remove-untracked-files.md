**Title Tag**: Removing Untracked Files with Git

**Meta Description**: Did you know that files in your Git repository can be either tracked or untracked? Find about what to do with untracked files and how to remove them, if needed. Learn Git with CareerKarma.

**Slug**: /git-remove-untracked-files/

**Target Keywords**: Git, Remove Untracked Files, Git Clean, Gitignore

**Author**: Felipe Bohorquez

**Twitter Message**: Did you know that files in your #GitRepository can be either tracked or untracked? Find about what to do with untracked files and how to remove them, if needed. Learn #Git with #CareerKarma.

**Word-Range**: 1000 words

**STATUS**: Done

---

# Removing Untracked Files with Git

We'll learn how remove untracked files with Git. Why should we remove untracked files? Because either we could have our working (local) directory cluttered by unused files, you pointed Git to a folder you didn't wanted to, there are leftover files from other merges, or simply you want to remove certain files. There's a way we can do that with Git.

## Difference Between Tracked vs. Untracked Files

In your working or local directory your files are either tracked or untracked. **Tracked** means those files added and committed in a previous snapshot and that Git is aware, tracking them for changes. 

**Untracked** files are just the opposite, those files were not in the previous commit and have not been staged to be committed. You have the option of either stage them and then commit them to your repository or remove them!

If we do `git status` right after modifying/added files it would show us the list of untracked files and files that are tracked and ready to be committed with new changes.

## Removing Untracked Files Option 1: `gitignore`

The first option would not remove them but rather **ignore** such files. You could be working on a C++ project that during build you might get files generated you don't want publicly available. You could also be working on your Node backend for an exciting project and you have your `.env` file with all your environment variables and database, API, access keys. You wouldn't want that info be out there in the wild either right? This is where `.gitignore` comes to play.

Any files that are present in a `.gitignore` file will not be part of the untracked vs tracked Git flow. They'll basically be 'removed' from it, so Git will ignore them and not track them nor complain they are not tracked. How do we go about doing this?

First let's create a `.gitignore` file in root. And then we'll specify the relative path of the location so if let's say we want to hide the node_modules and config.evn file we just add them as such:

```bash
node_modules
config.env
```

Understanding Gitignore is essential as your project grows so you must be aware which folders, files need to be added there because you don't want them in the Git workflow as untracked to them stage them by mistake and have Git tracking them for everyone to see your keys exposed!

## Removing Untracked Files Option 2: `git clean`

The next option we have to remove the files is to use the `git clean` command. This would be useful in case you accidentally point your working directory to your silly high school pictures you always wanted to delete but didn't have time to do so.

Git clean takes a couple of options so let's take a look at them:

`git clean [-d] [-f] [-i] [-n] [-q] [-e <pattern>] [-x | -X] [--] <path>…​`

This sounds complicated but we should understand that this command should accept one of the options in order to work correctly. 

### `git clean -d -n`

If we don't specify a path we often wanna include the `-d` option to look into untracked directories as well. Now for starters we should include the **dry run option first** so that Git can warn us what will be removed so we end up with the `git clean -d -n` command. Let's look this in action, let's say we have sillyPicture.jpg we don't want to track and want to remove:

![Screen Shot 2020-09-09 at 10 21 46 PM](https://user-images.githubusercontent.com/15071636/92678123-e36c0e00-f2ea-11ea-8e04-e2014f65a1dc.png)

Note if you are unsure at this point how does the `-d` option work just go ahead and do not use it until well understood to avoid unnecessary deletions. Just go ahead and add the path whenever you need to remove an specific untracked file.

### `git clean -f` or `git clean -d -f`

At this point it is worth mentioning that **Git clean actually deletes your file in hard system way (meaning you cannot undo once done)**. So it is similar to the `rm` command in terminal. 

Now **in order to to Git clean to work, we need to specify a force option or it will not work**. Let's go ahead and remove our sillyPicture.jpg with `git clean -f` or more specifically as `git clean -f sillyPicture.jpg`

![Screen Shot 2020-09-09 at 10 42 31 PM](https://user-images.githubusercontent.com/15071636/92679422-00561080-f2ee-11ea-8c77-aad69740b4d2.png)

Ok so here you might notice that here git status first noticed there was an untracked file, then after we deleted with the `-f` option the file was then gone, finito!

Although the `-f` option and Git clean is very powerful, it will not work with ignored files, because only works with files git is aware and are part of its version control system.

### `git clean -x`

This is not recommended unless you really know what you are doing. Yes you can remove ignored files and directories how just using the `-x` option. So `git clean -d -x -f` will do that as easy as the blink of an eye. 


### `git clean -d -i`

**Recommended for beginners**. As you're getting started you might want to be careful of what options you pass in. We already show you the dry run `-n` option. There's also the `-i` option that will show you an interactive interface you can play with!

![Screen Shot 2020-09-09 at 10 56 30 PM](https://user-images.githubusercontent.com/15071636/92680157-d0a80800-f2ef-11ea-8905-62175b19c433.png)


## Conclusion

You might wonder at this point why not just delete them the files you don't need like you regularly do with any other file on your computer? Well, because if you are entirely sure these files are irrelevant then there's no purpose to have them in the trash can. And if all you want is for Git to ignore them, well we already show you the first way, which is to ignore those from the Git version control system, by adding them to the Gitignore file. 
