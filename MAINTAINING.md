# Maintaining
Documentation for the development process and guidelines for project maintainers.

### Pull requests

Pull requests are expected to be made into ``master`` from branches with the following naming convention and corresponding to an open issue:

```
issue/<issue-number>-<description>
```

Do not use GitHub's merge option. Instead, checkout the whole branch and test the changes locally, sorting out any problems with the integration before merging into ``master`` and pushing to the remote.

### Release checklist

- Update the version number in package.json and elementary.scss.
- Use a dedicated commit to bump the version number. The commit message must be in the format ``v1.0.0``. In the same commit, update the CHANGELOG with a list of functional changes.
- Create an annotated tag on the appropriate ``master`` branch: ``git tag -a v1.0.0 -m "Tagging v1.0.0"``.
- Push the changes and tags: ``git push --tags origin master``.
- Update the  website by checking out the ``gh-pages`` branch and following the instructions in the README in that branch.

### Semantic versioning

[Semver](http://semver.org/) is the gold standard for software version numbering. Version numbers are written as ``v<major>.<minor>.<patch>``, e.g. ``v1.0.5``.

_Any_ change to _any_ CSS selector or rule will break backwards compatibility. Therefore, all CSS changes will increment the major version number. Comments and formatting changes will bump the patch number. There is no type of change that can be made to CSS that is considered to be minor.

### Standards

Elementary CSS is compatible with modern web standards. No effort is made to deal with HTML elements that have been deprecated from the HTML5 specification, things like ``<acronym>`` and ``<center>``. New HTML elements that have been recently added to the specification but which are not yet widely supported, things like ``<menu>``, are also omitted.

### Compatibility

Once a browser release dips below 1% global market share _in the browser's category_, the minimum supported version is bumped. Note that category share is higher than total market share. For example, Microsoft Edge has about a 1% total market share, but more than 3% in the desktop category and higher still among Windows users.
