Git-switch
==========

A git command for stashing and checking out in one operation.

When juggling a pile of branches, with constant interruptions, it can become quite a hassle to remember committing or stashing your work all the time. It did for me, anyway, which is why I made this little tool.

I use this daily, but do so at your own risk. I make no guarantees.

##Installing

Place the script file somewhere in your PATH. I've placed mine in Git/libexec/git-core, but anywhere in PATH should do.

##Using

    git switch other_branch

To enable tab-completion of branch names, add the following line to (Linux) /etc/bash_completion.d/git or
(Git Bash) /etc/git-completion.bash

    __git_complete "git switch" _git_checkout
##How it works

Git-switch will stash local changes to your working copy (if any), check out the other branch, and - if one is found - apply, and drop, the stash matching the branch you are checking out.

Basically (pseudo code):

    git stash save 'SWITCH-current_branch'
    git checkout other_branch
    git stash apply SWITCH-other_branch
    git stash drop SWITCH-other_branch

only with a lot more checking and verification of valid states

##License

None, zip, zilch - use, modify, redistribute or sell any way you like, at your own risk.