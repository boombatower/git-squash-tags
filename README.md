git-squash-tags
===============
Squash commit history to single commit per tag.

Useful when deploying a framework or large repository to web services that use a git repository as
the deployment mechanism. Instead of including a whole bunch of history bloat only keep commits for
each tagged release. Pulling in new releases or rebasing project commits on top still works as
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

To change some default parameters see online help:

```sh
$ git-squash-tags --help
```

To continue with existing squash branch and only process new commits start on the primary branch
and launch the script with the same parameters. It will detect the existing squashed branch and commits.

Example
-------
https://github.com/boombatower/drupal-squash

See `.travis.yml` for automating generation of squashed branch and `update.php` for triggering new
builds when changes are made upstream.
