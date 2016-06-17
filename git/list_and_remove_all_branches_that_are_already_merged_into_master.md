# List all branches that are already merged into master (and remove them)

After working on a repo for a while, you probably have many branches that already merged to master. If you want to clean them up, here are the ways to view and remove them.

List all branches that are already merged into master:
```bash
git branch --merged master
```

And you can also remove all the branches that already merged to master
```bash
git branch --merged master | grep -v '^\*' | xargs -n 1 git branch -d
```

![Branches got clean] (./clean_branches.png?raw=true)

Isn't it great to have a clean repo after clean up? :)

[source](https://github.com/git-tips/tips)
