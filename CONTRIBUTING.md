# Contributing

All contributions – bug reports, feature requests, and material changes to the source code – are managed via the project's [issue tracker](https://github.com/kieranpotts/elementary/issues).


## Feature requests

Feature requests are welcome. Feature requests may be submitted via the [issue tracker](https://github.com/kieranpotts/elementary/issues). Please add the "enhancement" label and prefix the title "Idea:".

Take a moment to consider whether your idea fits with the scope and aims of the project, and what are the benefits versus costs of adding the feature.


## Bug reports

Before reporting a bug, please check that it has not already been reported previously by searching the [issue tracker](https://github.com/kieranpotts/elementary/issues). Also check that the problem has not already been fixed by trying to reproduce the problem in the ``master`` branch.

To fix an error, the software maintainers must be able to reproduce it. This requires you to be able to demonstrate the bug. A good bug report will therefore include at least one of the following:

- Detailed step-by-step instructions to reproduce the error.
- A live example of the problem, e.g. a [Codepen](http://codepen.io/).
- A reduced test case, like the ones in our ``./tests/`` directory.

Please provide details of the browser name, version number, and operating system in which you experienced the error. Describe the outcome your expected, and what's different about the actual outcome.

If you can identify the source of the bug, such as a specific line or block of code, please include this information in your bug report, too.


## Source changes

The ultimate way to contribute to any open source software project is to help makes changes to its source code, tests, and documentation. This is done using the pull request (PR) system. 

Please raise an issue before making a pull request. The project maintainers will review your bug report or feature request, and they will accept or reject it before you spend time implementing the fix or enhancement.

The fork-and-branch workflow is used to manage changes to the project's source code. This allows individual contributors to work in isolation without interfering with anyone else's work.

The steps are as follows:

### 1. Fork

From the project's GitHub page, click "Fork". The project's repository will be cloned in your own GitHub account. The fork is your "origin" repository, while the main project repository is referred to as the "upstream" repository.

### 2. Clone

Download a copy of your origin repository:

```
git clone https://github.com/<your-github-username>/elementary.git
```

The copy of the project that now exists on your computer is your "local" repository. This is where you'll do your work. 

When you run the ``git clone`` command, Git automatically adds a remote named "origin", which you will push back to when you've made changes in your local repository. You should add another remote that references the upstream repository. From the root directory of your newly cloned local repository, run the following command in your terminal:

```
git remote add upstream https://github.com/kieranpotts/elementary.git
```

### 3. Checkout

Checkout the ``master`` branch:

```
git checkout master
```

If you want to make changes to a previous release, checkout the relevant version branch instead. Example:

```
git checkout master/v1
```

Pull down the contents of this branch from your origin repository:

```
git fetch origin
git merge origin
```

These two commands are equivalent to ``git pull origin master``.

### 4. Branch

Never make commits directly into ``master``. Instead, branch off from ``master`` to create a temporary branch, where you will make your changes. Please use the following naming convention for the new branch: 

```
issue/<issue-number>-<description>
```

``<issue-number>`` is the number of the issue that you opened in our issue tracker. ``<description>`` is a concise slug that describes the feature or bug. Example:

```
issue/21-improve-pre-line-height
```

Following this naming convention will help the project maintainers to review and integrate your work later, because each pull request will explicitly reference an open issue.

Use the following ``git`` commands to create and checkout the issue branch:

```
git branch issue/<issue-number>-<description>
git checkout issue/<issue-number>-<description>
```

Or more succinctly:

```
git checkout -b issue/<issue-number>-<description>
```

Example:

```
git checkout -b issue/21-improve-pre-line-height
```

### 5. Commit

Undertake your work in your issue branch.

If you are making substantive changes over a long period, you should make regular commits, organizing your changes in logical iterations. Long-lived feature branches should be kept synchronized with the project mainline, and you may like to backup your work by pushing regularly to your origin repository on GitHub. See below for instructions.

Be sure to add or update the relevant reduced test cases, which are in the ``./tests`` directory. The reduced test cases are plain HTML documents that demonstrate the effect of the Elementary CSS style sheet on isolated HTML elements.

Make your changes, and stage and commit them. Using the ``-a`` flag on commit will allow you to submit a commit subject plus a more detailed body message, if you wish.

```
git add
git commit -a
```

### 6. Synchronize

If it has been a while since you cloned and checked out the project, you should fetch the latest changes from the ``master`` branch in the upstream repository.

```
git checkout master
git pull upstream master
```

Return to your issue branch and [rebase](https://help.github.com/articles/about-git-rebase/) it on ``master``.

```
git checkout issue/21-improve-pre-line-height
git rebase -i --autosquash master
```

As a shortcut, you can rebase the upstream ``master`` branch directly into your local issue branch:

```
git pull --rebase -i upstream master
```

The rebasing step will give you the chance to sort out conflicts with the latest work in the project mainline before you make a pull request. The result is that your PR will have a nice clean diff, so your work can be integrated faster. 

Interactive rebasing, using the ``-i`` or ``-interactive`` flag, is recommended. It will allow you to clean up your commit history before submitting your work. You can edit old commits, split them up, reorder them, and even squash some. If you have a particularly messy commit history, you may choose to use ``--autosquash`` to consolidate all of your work into a single commit. 

If you have conflicts, resolve them, and then continue the rebase.

```
git add <file1> <file2> ...
git rebase --continue
```

### 7. Push

Push the changes your local issue branch to your remote origin repository. Because rebasing changes history, you should use ``-f`` or ``--force`` to force changes into the remote.

```
git push -f origin issue/21-improve-pre-line-height
```

If someone else is working on the same branch, use the less destructive ``--force-with-lease``.


### 8. Pull request

Now all your work is in your origin repository, which is attached to your GitHub user account. From the GitHub page for your origin repository, issue a [pull request](https://help.github.com/articles/about-pull-requests/) to have your work merged in to the project's upstream repository. Click the "Pull Request" button on GitHub and follow the steps. Provide a clear title and description, and be sure to leave checked the option to "allow edits from maintainers". 

The maintainers of the upstream repository will review and merge your changes into the project.

_By opening a pull request, you agree to allow the project maintainers to license your work under the same terms as the project._

### 9. Tidy up

With everything pushed to the remotes, you can safely delete the temporary issue branch from your local repository.

```
git branch -d issue/21-improve-pre-line-height
```


## Guidelines for maintainers

### Pull requests

Pull requests are expected to be made into ``master`` from branches with the following naming convention and corresponding to an open issue:

```
issue/<issue-number>-<description>
```

Do not use GitHub's merge option. Instead, checkout the whole branch and test the changes locally, sorting out any problems with the integration before merging into ``master`` and pushing to the remote.

### Release checklist

- Update the version number in package.json and elementary.scss.
- Use a dedicated commit to bump the version number. The commit message must be in the format ``v1.0.0``. In the same commit, update the CHANGELOG with a list of functional changes.
- Create an annotated tag on ``master`` for the release: ``git tag -m "v1.0.0" v1.0.0``.
- Push the changes and tags: ``git push --tags origin master``.
- Update the  website by checking out the ``gh-pages`` branch and following the instructions in the README in that branch.

### Semantic versioning

[Semver](http://semver.org/) is the gold standard for software version numbering. Version numbers are written as ``v<major>.<minor>.<patch>``, e.g. ``v1.0.5``.

_Any_ change to _any_ CSS selector or rule will break backwards compatibility. Therefore, all CSS changes will increment the major version number. Comments and formatting changes will bump the patch number. There is no type of change that can be made to CSS that is considered to be minor.

### Standards

Elementary CSS is compatible with modern web standards. No effort is made to deal with HTML elements that have been deprecated from the HTML5 specification, things like ``<acronym>`` and ``<center>``. New HTML elements that have been recently added to the specification but which are not yet widely supported, things like ``<menu>``, are also omitted.

### Compatibility

Once a browser release dips below 1% global market share _in the browser's category_, the minimum supported version is bumped. Note that category share is higher than total market share. For example, Microsoft Edge has about a 1% total market share, but more than 3% in the desktop category and higher still among Windows users.
