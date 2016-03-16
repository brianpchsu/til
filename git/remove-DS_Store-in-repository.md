# Remove .DS_Store files from a Git repository?

If you use Mac OSX sytem, you might see the .DS_Store file in your git repository. You don't want to store that file in your commit history. So here is the way to remove it.

Remove existing files from the repository:
```bash
find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
```

And add the following line to your .gitignore file
```
.DS_Store
```

You will have a clean repo now.

[source](http://stackoverflow.com/a/107921/3525493)
