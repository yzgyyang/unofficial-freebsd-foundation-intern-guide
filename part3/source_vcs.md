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

Then, `git merge` or `git rebase` can be used to keep your own repositories updated.

Here shows how to use `git merge`. `git rebase` should be similar.
```
git fetch upstream master
git merge upstream/master
{Possibly create a merge commit automatically}
```

Alternatively, clone the repositories directly to local, but your changes will be harder to keep track of in the future.

### Start Your Git Workflow

Use your own Git workflow on your own repositories, as only the final patch will be submitted.

When submitting a patch, use `git diff` to create a differential revision. More details [here](part4/diff.md).
