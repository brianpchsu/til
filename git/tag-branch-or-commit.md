# Tag branch or commit from a Git repository

If you are developing your library and want to use certain branch or commit before it merged to master, you can tag specific branch or commit by the following steps:

Tag specific branch from the repository
```bash
$ git tag -a v1.2 bugfix/connection-restore -m "Explain tag message here..."
```

Tag specific commit from the repository:
```bash
$ git tag -a v1.3 c543edksk123sfjdskjfksdjl -m "Tag message for this commit"
```

And in your package.json or bower.json dependencies, chose the version you like to use
```
"dependencies": {
  ...
  "brian-library": https://source.brianpchsu.com/repo/brian-library.git#v1.2
  ...
}
```

[source](http://stackoverflow.com/a/14613683/3525493)
