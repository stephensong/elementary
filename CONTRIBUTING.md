
# Contributing to Elementary CSS

This is a free and open source software project. It is made possible by generous contributions from software engineers, both expert and novice, from around the world.

If you would like to take part in this project, please create an issue in the project's [issue tracker](https://github.com/kieranpotts/elementary/issues). This is the exclusive channel by which all contributions – bug reports, feature requests, and material changes to the source code – are managed.


## Feature requests

Feature requests are welcome. Feature requests may be submitted via the [issue tracker](https://github.com/kieranpotts/elementary/issues). Please add the "enhancement" label and prefix the issue title "Idea:".

Take a moment to consider whether your idea fits with the scope and aims of the project, and what are the benefits versus costs of adding the feature.


## Bug reports

Before reporting a bug, please check that it has not already been reported previously by searching our [issue tracker](https://github.com/kieranpotts/elementary/issues), and check that it is not already been fixed by trying to reproduce the problem in the ``master`` branch.

In order to fix an error, the software maintainers must be able to reproduce it. This requires you to be able to demonstrate the bug. A good bug report will therefore include at least one of the following:

- Detailed step-by-step instructions to reproduce the error.
- A live example of the problem, e.g. a [Codepen](http://codepen.io/).
- A reduced test case, like the ones in our ``./tests/`` directory.

Please provide details of the browser name, version number, and operating system in which you experienced the error. Describe the outcome your expected, and what's different in the actual outcome.

If you are able to identify the source of the bug, such as a specific line or block of code, please include this information in your bug report, too.


## Source changes

The ultimate way to contribute to any open source software project is to help makes changes to its source code, tests, and documentation. This is done using the pull request (PR) system. Please raise an issue before making a pull request. The project maintainers will review your bug report or feature request, and they will accept or reject it before you spend time implementing the fix or enhancement.

The fork-and-branch workflow is used to manage changes to the project's source code. This allows individual contributors to work in isolation without interfering with anyone else's work.


### 1. Fork

From the project's GitHub page, click "Fork". The project's repository will be cloned in your own GitHub account. The fork is your "origin" repository, while the main one is referred to as the "upstream" repository.


### 2. Clone

Download a copy of your origin repository:

```
git clone https://github.com/<your-github-username>/elementary.git
```

The copy of the project that now exists on your computer is your "local" repository. This is where you'll do your work. 

When you run the ``git clone`` command, Git automatically adds a remote named "origin", which you will push back to when you've made your changes in your local repository. You should add another remote that references the upstream repository. From the root directory of your newly cloned local repository, run the following command in your terminal:

```
git remote add upstream https://github.com/kieranpotts/elementary.git
```


### 3. Checkout the project's mainline

Checkout the ``master`` branch:

```
git checkout master
```

If you want to make changes to a previous release, checkout the relevant version branch instead. Example:

```
git checkout master/v1
```

(Note that we do not use a ``develop`` branch in our workflow.)

Pull down the contents of this branch from your origin repository:

```
git fetch origin
git merge origin
```

(These two commands are equivalent to ``git pull origin master``.)


### 4. Branch from the mainline

Never make commits directly into ``master``. Instead, branch off from ``master`` to create a temporary branch, where you will make your changes. Please use the following naming convention for your feature branch: 

```
issue/<issue-number>-<description>
```

Where ``<issue-number>`` is the number of the issue that you created in the issue tracker. Following this naming convention will help the project maintainers to review and integrate your work later.

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
git checkout -b issue/51-preformatted-text-line-height-increase
```


### 5. Do your work

Undertake your work in your feature branch.

If you are making substantive changes over a long period of time, you should make regular commits, organising your changes in logical iterations. Also, long-lived feature branches should be kept synchronised with the project mainline, and you may like to backup your work as you go by pushing to your origin repository on GitHub. See the next steps for instructions.

Be sure to add or update the relevant reduced test cases, which are in the ``./tests`` directory. The reduced test cases are plain HTML documents that demonstrate the effect of the Elementary CSS style sheet on isolated HTML elements.


### 5. Stage and commit changes

Make your changes, and stage and commit them. Using the ``-a`` flag on commit will allow you to submit a commit subject plus a more detailed body message, if you wish.

```
git add
git commit -a
```


### 6. Synchronise with the project's mainline

If it has been a while since you cloned and checked out the project, you should fetch the latest changes from the ``master`` branch in the upstream repository.

```
git checkout master
git pull upstream master
```

Return to your feature branch and rebase it on ``master``. The rebasing step will give you the chance to sort out conflicts with the latest work in ``master`` before you make a pull request. The result is that your PR will have a nice clean diff with the project mainline, so your work can be integrated faster. Interactive rebasing, using the ``-i`` or ``-interactive`` flag, is recommended. It will allow you to clean up your commit history before submitting your work. You can edit old commits, split them up, reorder them, and even squash some. If you have a particularly messy commit history, you may choose to use ``--autosquash`` to consolidate all of your work into a single commit. 

```
git checkout issue/<issue-number>-<description>
git rebase -i --autosquash master
```

As a shortcut, you can rebase the upstream ``master`` branch directly into your local feature branch:

```
git pull --rebase -i upstream master
```

If you have conflicts, resolve them, and then continue the rebase.

```
git add <file1> <file2> ...
git rebase --continue
```


### 7. Push

Push your local feature branch to your remote origin repository. Because rebasing changes history, you should use ``-f`` or ``--force`` to force changes into the remote.

```
git push -f origin issue/<issue-number>-<description>
```

If someone else is working on the same branch, use the less destructive ``--force-with-lease``.


### 8. Pull request

Now all of your work is in your origin repository, which is attached to your GitHub user account. From the GitHub page for your origin repository, you can issue a [pull request](https://help.github.com/articles/about-pull-requests/) to have your work merged in to the project's upstream repository. Click the "Pull Request" button on GitHub and follow the steps. Provide a clear title and description, and be sure to leave checked the option to "allow edits from maintainers". 

The maintainers of the upstream repository will review and merge your changes into the main project.

**IMPORTANT: By opening a pull request, you agree to allow the project maintainers to license your work under the same terms as the project.**


### 9. Tidy up

With everything pushed to the remotes, you can safely delete your feature branch from your local repository.

```
git branch -d issue/<issue-number>-<description>
```
