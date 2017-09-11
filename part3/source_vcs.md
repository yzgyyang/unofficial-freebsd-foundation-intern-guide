# Source and Version Control Systems

Currently the official version control system for the FreeBSD Project is Subversion(SVN). A git read-only mirror is also available on GitHub.

## Using SVN

A comprehensive guide is available in the Handbook.

## Using Git

The 3 main repositories (src, ports, doc) are all available on GitHub as mirrors (which means no Issues or Pull Requests are accepted). However, if git is preferred, and if you are working as a contributor and committing code through other committers only (exactly the situation during the internship), you can totally live on Git and never worry about SVN.

### Get a Copy and Set it up

Fork one or more of the repositories to your GitHub account from https://github.com/freebsd.

Then clone it to local:
```
git clone https://github.com/{your-git-username}/{freebsd, freebsd-ports, freebsd-doc}
```

Set up to keep track of remote repositories:
```
git remote add upstream https://github.com/freebsd/{freebsd, freebsd-ports, freebsd-doc}
```

Check if the upstream has been added correctly:
```
git remote -v
```

Then, to keep your local repository updated with FreeBSD CURRENT, run the following while in the master branch:
```
git pull upstream master
```
Note: due to the size of the repositories and the large number of commits that arrive in CURRENT every day, updating your local repository could cause a large increase in the time it takes to run a full rebuild. This is especially true for the `freebsd-src` repository.

Alternatively, clone the repositories directly to local, but your changes will be harder to keep track of in the future.

### Start Your Git Workflow

Use your own Git workflow on your own repositories, as only the final patch will be submitted.
The following was Siva's workflow for working on one patch from end to end in the `freebsd-src` repository:

1. Checkout a new local branch off of master. NOTE: it is recommended *not* to update the local master branch with FreeBSD CURRENT before doing this because it will minimize the time taken to rebuild after changes are made to the new branch.
2. Make changes required for the patch to work, rebuilding the project as necessary.
3. Submit the patch for review, making subsequent commits as needed
4. Determine whether your changes conflict with any changes made to FreeBSD CURRENT after you first made your local branch.
If they do (or might) conflict, update your master branch with FreeBSD CURRENT and rebase your new branch against the updated master.
5. (optional): Push your branch to your local fork, signifying that the change is ready to commit.

When submitting a patch, use `git diff` to create a differential revision. More details [here](part4/diff.md).
