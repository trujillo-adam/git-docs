## What is the difference between push, pull, and fetch?
This topic provides an overview of the `git push`, `git pull`, and `git fetch` commands and when to use them.
### About the `git push` command
Use this command to update a branch in a remote repository with changes in your local branch. This enables you to share changes with others working with the same repository. The `git push` command performs the following operations:

1. Checks if the current local branch is being tracked in a remote repository.  
1. If the branch is tracked is tracked in a remote repository, the remote branch is updated with changes contained in the local branch.

The commit history for the local and remote branch must be in sync. The operation will fail if the local branch does not have all commits that were made to the remote branch. Synchronize your local branch with the remote branch if this occurs by executing the following commands:

`git pull` or `git fetch`

`git merge`

### About the `git pull` command
This command performs the following operations:
1. First, it fetches changes from a remote branch into your tracking branch.
1. Next, it merges them into a local branch.

You can run a `git fetch` command followed by a `git merge` command to achieve the same result. Running separate commands enables you to review the changes before merging them.  

### About the `git fetch` command
Use the this command to get changes from a remote repository and add them to your tracked branch. It performs the following operations:
1. Checks if the current local branch is tracked in a remote repository.
1. If the remote branch contains newer changes for the local branch, the git pulls the changes into the tracking branch.

This command does not merge the changes from the remote repository into your local branch. You can run the following command in order to merge the changes:  

`git merge origin <BRANCH>`

Note that the default branch for a git repository is the "master" branch. Unless you created or switched to a different branch, you will likely merge changes on the master branch.

Often `git push` and `git pull` are described as equivalent. ~~This isn't entirely correct, since under the hood `git pull` does two things. `git push` takes our current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, our changes are taken from our branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.~~ ~~`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".~~ ~~`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.~~
