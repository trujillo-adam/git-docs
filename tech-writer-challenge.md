## Using git push, pull, and fetch
This topic provides an overview of the `git push`, `git pull`, and `git fetch` commands.

### `git push`
Use this command to update the remote repository with changes in your local branch. This enables you to share changes with other people working from the same repository. The `git push` command performs the following operations:

1. Checks if the current local branch is being tracked in a remote repository.  
1. If the branch is tracked in a remote repository, the remote branch is updated with changes contained in the local branch.

The commit history for the local and remote branch must be in sync. The operation will fail if the local branch does not have all commits that were made to the remote branch. Synchronize your local branch with the remote branch if this occurs by executing the following commands:

1. `git pull` or `git fetch`

1. `git merge`

### `git pull`
Use this command to fetch changes from a branch on the remote repository and merge them into your local branch. This command performs the following operations:

1. Fetches changes from a remote branch into your tracking branch.
1. Merges them into a local branch.

You can run a `git fetch` command followed by a `git merge` command to achieve the same result. Running separate commands enables you to review the changes before merging them.  

### `git fetch`
Use the this command to get changes from a remote repository and add them to your tracked branch. It performs the following operations:

1. Checks if the current local branch is tracked in a remote repository.
1. If the remote branch contains newer changes for the local branch, the git pulls the changes into the tracking branch.

This command does not merge the changes from the remote repository into your local branch. You can run the following command in order to merge the changes:  

`git merge origin <BRANCH>`

Note that the default branch for a git repository is the "master" branch. Unless you created or switched to a different branch, you will likely merge changes on the master branch.
