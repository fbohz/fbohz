**Title Tag**: Gitignore Not Working

**Meta Description**: Do you really know what the HTML form tag action attribute is? Is it required on all forms? Learn HTML with CareerKarma.

**Slug**: /gitignore_not_working/

**Target Keywords**: Git, Gitignore, Gitignore Not Working.

**Author**: Felipe Bohorquez

**Twitter Message**: Do you really know what the #HTML form tag action attribute is? Is it required on all forms? Learn #HTML with CareerKarma.

**Word-Range**: 500 words

**STATUS**: DONE

---

# Gitignore Not Working

The title says it all. There are many cases where you might be troubleshooting `.gitignore` file because it is not working as expected. Here we'll discuss two scenarios and its possible solutions. 


## What is the Gitignore File

The gitignore file is probably one of the most important files for you to understand whenever you use Git. This file should be named and saved explicitly as `.gitignore`. On this plain text file, you would then add the paths of files or directories you want Git to not track. So whatever it is added here Git will basically ignore and not add to its tracking tree. 

Here's an example of a gitignore file contents:

```bash
node_modules/
.env
```

On this file we basically are telling Git to ignore our `.env` file which often contains API keys and the node_module folder that contains all installed NPM packages.


## Scenario A: Adding a File to Gitignore after Committing it 

We could complain why gitignore is not working after we mistakenly committed a file that was supposed to be ignored then after adding it to gitignore, Git is still tracking it. 

Well the reason for this is that **we need to add files/folders before committing them**. Git is already tracking them, so we will need to do the following command:

`git rm -rf --cached <path>`

The first part `git rm` removes the `<path>`, and `--cached` specifies it is removed from the index but stays in local directory. `r` is recursive removal if given a directory path and `f` forces it. So it will delete them. If you are working with a file and **still wanna keep it on your local** do:

`git rm --cached <file>`

This will keep the file in your working directory. So with this you are indicating Git that you don't want to track the file/folder provided anymore.

## Scenario B: Gitignore Created Before Committing and Still Not Tracking Files

If this is the case, then the solution might be simple and you might actually have to check that you are providing the correct path and file name. Also check that you don't have any trailing space at the beginning nor end of file declarations. 

## Conclusion

We discussed few scenarios and possibilities of solutions for various cases when gitignore wasn't working as expected. The main takeaway is that you must understand where the files/directories are located so you can add the correct path. You must also be aware that as soon as you create a file that needs to be ignored add it to gitignore **right away**. If you happen to have committed it by mistake, luckily we have the `git rm -rf --cached <path>`/ `git rm --cached <file>` command that will take it out from the Git workflow.

**Note:** There might be other cases that Git reset might be useful, I wrote an article regarding [Git Reset](https://careerkarma.com/blog/git-reset/) that will be useful on these cases. So Git reset will be like undoing, so in some cases that is what you want.