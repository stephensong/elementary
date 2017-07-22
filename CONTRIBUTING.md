
# Contributing

This is a free and open source software project. It is made possible by generous contributions from software engineers, both expert and novice, from around the world.

If you would like to take part in this project, please create an issue in the project's [issue tracker](https://github.com/kieranpotts/elementary/issues). This is the exclusive channel by which all contributions – bug reports, feature requests, and material changes to the source code – are managed.

The ultimate way to contribute to any open source software project is to submit material changes to its source code, tests, and documentation. This is done using the pull request (PR) workflow. Please raise an issue before submitting pull requests. The project maintainers will review your bug report or feature request, and they will accept or reject it before you spend time implementing the fix or enhancement.


## Pull requests

The fork-and-branch workflow is used to manage changes to this project's source code. It allows individual contributors to work in isolation without interfering with anyone else's work.

From the project's GitHub page, click "Fork". The project's repository will be cloned in your own GitHub account. The fork is your "origin" repository, while the original is referred to as the "upstream" repository.

Download a copy of your origin repository:

```
git clone https://github.com/<your-github-username>/elementary.git
```

The copy of the project that now sits on your hard drive is your "local" repository. This is where you'll do your work. When you run the ``git clone`` command, Git automatically adds a remote named "origin", which you will push back to when you've made your changes in your local repository.

Checkout the ``master`` branch:

```
git checkout master
```

If you want to make a change to a previous version, checkout the relevant version branch. For example:

```
git checkout master/v1.0
```

(We don't use a ``develop`` branch.)

Pull down the contents of this branch from your origin repository:

```
git fetch origin
git merge origin
```

(These two commands are equivalent to ``git pull origin master``.)

In your local repository, branch off from the master branch to create a temporary feature branch. We recommend that you name this branch "issue/<issue-number>-<description>" where "<issue-number>" is the number of the issue that you raised in the upstream repository's issue tracker. Example:

```
git branch issue/51-preformatted-text-line-height-increase
git checkout issue/51-preformatted-text-line-height-increase
```

Or more succinctly:

```
git checkout -b issue/51-preformatted-text-line-height-increase
```

Following our naming convention for issue branches will help the project maintainers to review and integrate your work later.

Make your changes, and stage and commit them. Using the ``-a`` flag on commit will allow you to submit a commit subject plus a more detailed body message, if you wish.

```
git add
git commit -a
```

When you have finished your work, please merge in the latest changes from the ``master`` branch in the upstream repository. To do that, you will need to add another remote pointing to the upstream repository:

```
git remote add upstream https://github.com/kieranpotts/elementary.git
```

Next, synchronise your local ``master`` branch with the upstream's ``master``: 

```
git checkout master
git fetch upstream master
```

Now, return to your issue branch and rebase it on ``master``. The rebasing step will also give you the chance to sort out conflicts with ``master`` before you create a pull request. Interactive rebasing, using the ``-i`` or ``-interactive`` flag, is recommended. It will allow you to clean up your commit history before submitting your work. You can edit old commits, split them up, reorder them, and even squash some. If you have a particularly messy commit history, you may choose to use ``--autosquash`` to squash all of your work into a single commit. 

```
git checkout issue/<issue-number>-<description>
git rebase -i --autosquash master
```

If you have conflicts, resolve them, and then continue the rebase.

```
git add <file1> <file2> ...
git rebase --continue
```

Push your local issue branch to your remote origin repository. Because rebasing changes history, you should use ``-f`` or ``--force`` to force changes into the remote. If someone else is working on the same branch, use the less destructive ``--force-with-lease``.

```
git push -u -f origin issue/<issue-number>-<description>
```

Now all of your work is in your origin repository, which is attached to your GitHub user account. From there, you can issue a pull request to have your work merged in to the project's upstream repository. Click the "Pull Request" button on GitHub and follow the steps. Be sure to leave checked the "Allow edits from maintainers" option. The maintainers of the upstream repository will review and merge your changes into the main project.

With everything pushed to the remotes, you can safely delete your temporary issue branch from your local repository.

```
git branch -d issue/<issue-number>-<description>
```
