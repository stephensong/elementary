
# Notes for Project Maintainers

## Pull requests

Pull requests are expected to be made from branches with the following naming convention and corresponding to an open issue:

```
issue/<issue-number>-<description>
```

Do not use GitHub's merge option. Instead, checkout the whole branch and test the changes locally, sorting out any problems with the integration before merging into ``master`` and pushing to the remote.


## Release checklist

- Update the version number in the CHANGELOG, package.json, and elementary.scss.
- List functional changes in the CHANGELOG.
- Use a dedicated commit to bump the version number. The commit message must be in the format ``v1.0.0``.
- Create an annotated tag on ``master`` for the release: ``git tag -m "v1.0.0" 1.0.0``.
- Push the changes and tags: ``git push --tags origin master``.
- Update the  website by checking out the ``gh-pages`` branch and following the instructions in the README.


## Semantic versioning

[Semver](http://semver.org/) is the gold standard for software version numbering. Version numbers are written as ``v<major>.<minor>.<patch>``, e.g. ``v1.0.5``.

_Any_ change to _any_ CSS selector or rule will break backwards compatibility. Therefore, all CSS changes will increment the **major** version number. Comments and formatting changes will bump the **patch** number. There is no type of change that can be made to CSS that is **minor**. 

