# IP

#### Starting Work on a new Issue

If you haven't submitted changes for a request, you should first create a branch and pull-request.

1. Make sure you have no outstanding changes.
    - (from the project directory)
    - `> git status`
    - The resulting output should not list any files that are Changed or Untracked. If you have changes then please commit them, stash them or roll them back. Please contact the programmers or consult Git documentation for more info.
1. Get the latest Master copy of the project.
    - `> git checkout master`
    - `> git pull`
1. Create a new branch for your changes. Try to use the standard naming convention `issue-000` to match changes to the related redmine issue.
    - `> git checkout -b issue-000`
1. Synchronise this local branch back to BitBucket.
    - `> git push --set-upstream origin issue-000`


#### Restarting Work on a Previously-submitted Issue

If you have previously submitted a Pull Request for a branch and the branch has been closed by a merge of the Pull Request on BitBucket, you can still restart work on the same branch by re-using the `--set-upstream` parameter.

1. Make sure you have no outstanding changes.
    - (from the project directory)
    - `> git status`
    - The resulting output should not list any files that are Changed or Untracked. If you have changes then please commit them, stash them or roll them back. Please contact the programmers or consult Git documentation for more info.
1. Get the latest copy of your previous branch and push it back to the server.
    - `> git checkout issue/redmine-0000`
1. (optional) Merge (and conflict-resolve) any changes that have since been made to the master branch
    - `> git fetch origin master`
    - `> git merge --no-ff origin/master`
1. Re-open this local branch on BitBucket and synchronise any changes.
    - `> git push --set-upstream origin issue-000`

#### Submitting code changes

1. Make and test small, self-contained changes.
1. Use git to keep track what changes you have made
    - `> git status` Will list the files you have yet to commit along with details around your sync status to BitBucket
    - `> git diff <file> [...<file>]` Will show you each added/removed/changed line in a file since your last commit
1. Once you are happy with each change, commit it to your local branch.
    - `> git add <file>` or `> git add -A` Will add the changes you have made to a 'stage' that can then be committed.
    - `> git status` To ensure all the files you want to commit are listed in the 'stage' area.
    - `> git commit -m "Description of my change"` Will commit all staged changes ready to sync to BitBucket.
1. Before you leave your desk, sync the branch back to BitBucket again.
    - `> git push` Other contributors will now be able to see changes on BitBucket.
