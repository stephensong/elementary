
# Notes for Project Maintainers

## Managing Pull Requests

Pull requests are expected to be made from branches with the following naming convention and corresponding to an open issue:

```
issue/<issue-number>-<description>
```

Patches should have appropriate commit messages and tests.

Do not use GitHub's merge option. Instead, checkout the whole branch and merge it to ``master`` locally. Test the changes locally and sort out any problems with the integration before pushing to the remote ``master``.


## Release Checklist

- Update the version number in the CHANGELOG, package.json, and elementary.scss.
- List functional changes in the CHANGELOG.
- Use a dedicated commit to bump the version number. The commit message must be in the format ``v1.0.0``. Refer to the notes below on Semantic Versioning.
- Create an annotated tag for the version: ``git tag -m "v1.0.0" 1.0.0``.
- Push the changes and tags: ``git push --tags origin master``.
- Update the elementarycss.com website by checking out the ``gh-pages`` branch and following the instructions in the README.


## Semantic Versioning

[Semver](http://semver.org/) is the gold standard for software version numbering. Version numbers are written as ``v<major>.<minor>.<patch>``, e.g. ``v1.0.5``.

_Any_ change to _any_ CSS selector or rule will break backwards compatibility. Therefore, all CSS changes will increment the **major** version number. Comments and formatting changes will bump the **patch** number. There is no type of CSS change that is considered **minor**. 

