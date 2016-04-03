# Clone remote branch with git

When you clone a repo with git, you get the master branch. You can see all your local branches using

```
$ git branch
* master
```

What if you want to work on different branch?

First, you can see all the remote branches hiding in your clone repository.

```bash
$ git branch -a
* master
  remotes/origin/HEAD
  remotes/origin/master
  remotes/origin/test-camera
  remotes/origin/visualized-chart
  remotes/origin/experimental
```

If you want to work on an upstream branch, you'll need to create a local tracking branch:

```
$ git checkout -b experimental origin/experimental
```

And you will see
```
Branch experimental set up to track remote branch experimental from origin.
Switched to a new branch 'experimental'

```

Now, if you look at your local branches, this is what you'll see:
```
$ git branch
* experimental
  master
```

[source](http://stackoverflow.com/a/72156/3525493)
