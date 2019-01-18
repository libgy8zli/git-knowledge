# git-knowledge

from stackoverflow: https://stackoverflow.com/questions/948354/default-behavior-of-git-push-without-a-branch-specified/948397#948397


You can control the default behavior by setting push.default in your git config. From the git-config(1) documentation:

push.default
Defines the action git push should take if no refspec is given on the command line, no refspec is configured in the remote, and no refspec is implied by any of the options given on the command line. Possible values are:

nothing: do not push anything

matching: push all matching branches

All branches having the same name in both ends are considered to be matching.

This is the default in Git 1.x.

upstream: push the current branch to its upstream branch (tracking is a deprecated synonym for upstream)

current: push the current branch to a branch of the same name

simple: (new in Git 1.7.11) like upstream, but refuses to push if the upstream branch's name is different from the local one

This is the safest option and is well-suited for beginners.

This will become the default in Git 2.0.

The simple, current and upstream modes are for those who want to push out a single branch after finishing work, even when the other branches are not yet ready to be pushed out

Command line examples:

To view the current configuration:

git config --global push.default
To set a new configuration:

git config --global push.default current
