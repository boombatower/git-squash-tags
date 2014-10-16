git-squash-tags
===============
Squash commit history to single commits per tag.

Useful when deploying a framework or large repository to web services that use a git repository as
the deployment mechanism. Instead of including a whole bunch of history bloat only keep commits for
each tagged release. Pulling in new releases or rebasing project commit on top still works as
expected, but without the need to weight down the repository. Also makes it easy to distinguish
between project commits and base framework.

It may be a good idea to maintain a squashed mirror of the base repository outside of the project
repository.

Usage
-----
From the root of the repository to be squashed issue the following command which will squash the
commits in a new branch with the suffix `-squash`.

```sh
$ git-squash-tags
```

The script assumes the branch names are formatted similar to the tags. For example:

branch: 7.x
tags: 7.0, 7.1, 7.2

The first character of the branch is used for matching tags relevant to that branch. If a different
pattern is needed simply pass the pattern as the argument to the script.

```sh
$ git-squash-tags 8*
$ git-squash-tags something-weird*
```
