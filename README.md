# [![Elementary CSS](https://cdn.rawgit.com/kieranpotts/elementary/gh-pages/static/logo/elementary-css-logo.382x60.png)](https://www.elementarycss.com/)

Elementary CSS is an aggressive reset style sheet.

The principal purpose of a reset style sheet is to iron out inconsistencies in the default presentation given to HTML elements by web browsers. Elementary CSS goes further, overriding the browser's default style sheet to provide a more practical baseline from which to compose modern web application interfaces.


## Installation

Elementary CSS is not intended to be used as is. You are encouraged to fork and modify Elementary CSS for your own needs. You should change the fonts and colors and create your own set of base styles that are appropriate for your application's GUI.

Download the contents of the ``./src/`` directory and incorporate them into your project. You will need a Sass tool to compile ``./src/elementary.scss`` to CSS. Alternatively, you can use the pre-compiled ``./build/elementary.css`` or ``./build/elementary.min.css``.


## Features

As well as fixing common cross-browser inconsistencies, Elementary CSS implements the following changes to the browser's default styles. For a comprehensive list of changes, refer to the comments in ``./src/elementary.scss``.

### Typography

- The default font is changed to Roboto. 
- Inconsolata, a monospace font, is adopted for ``<pre>``, ``<code>``, ``<kbd>``, ``<samp>``, and ``<var>``.
- The root font size is changed from 16px to 10px, making it easier to specify relative sizes using root em (``rem``) units. For example, 1.2rem is rendered at 12px (1.2 x 10 = 12) on mobile devices.
- On large screens, the root font size is bumped, meaning that anything sized using rem units will scale proportionally to the rendering window.
- The non-standard ``text-size-adjust`` property is set to 100%, which is important for responsive designs as without this setting some browsers may attempt to resize text for better legibility.
- The default font color is changed to ``hsl(0, 0%, 10%)``, which is equivalent to the hex ``#1A1A1A``. 
- Properties such as ``color``, ``font-family`` and ``font-weight`` are made to be inherited by all elements that can contain text content, including ``<textarea>`` and ``<legend>`` which traditionally have not inherited such properties.
- The line height of all block-level text is set to be exactly equal to its font size by default.
- A consistent default presentation for the horizontal rule element (``<hr>``) is applied across all browsers. 
- Bullets are removed from unordered lists (``<ul>``), but numbering is persisted on ordered lists (``<ol>``) so that the useful ``type`` attribute still works: ``<ol type="A">``. 
- Only the ``<b>`` and ``<strong>`` elements are rendered with bold text, and only the ``<em>`` and ``<i>`` elements are italicized. Every other element, including ``<cite>`` and ``<address>``, is rendered in the normal font style. 
- Many other default text decorations are removed, such as underlines from ``<u>`` and ``<del>`` and the background color from ``<mark>``.
- The ``<small>`` element now adopts the ``font-size`` of its parent, turning this into a purely semantic element.
- Generated quotes are removed from ``<blockquote>`` and ``<q>``. 
- The default implementation of ``<sup>`` and ``<sub>`` affects line height in all browsers. A better methodology to render superscript and subscript text is implemented, one which does not affect line height.
- Where the non-standard ``text-rendering`` property is supported, it is set to ``optimizeLegibility``.

### Tables

- The default border model for tables is changed from ``separated`` to ``collapsed``, which is more convenient for styling. 
- Tables cells are configured to adjust their width automatically to best fit their content. 

### Multimedia

- Images and multimedia containers such as ``<video>`` are converted from inline to block-level display, and are made responsive by default.
- The ``<video>`` element is given a dark background color so that scaled-down videos are nicely letterboxed. 
- ``<audio>`` elements are not rendered if they don't have playback controls enabled.
- Embedded SVGs are configured to inherit the color of adjacent text as their default ``fill`` color. This is a handy hack for inline icons.

### Forms

- Form elements such as ``<label>``, ``<input>``, and ``<button>`` have their default ``display`` property changed to ``block``, since they are commonly rendered as block-level elements.
- The border is removed from ``<fieldset>`` elements.
- Placeholder text is given a consistent color across all browsers.

### Structure

- The modern clearfix hack is applied to sectioning elements such as ``<article>`` and ``<section>``, so these containers will always clear any nested floated content.
- The ``<address>`` element has been reclassified by the W3C as a sectioning element, so the legacy application of italics to text content within this element is removed.
- There's a fix in place for IE 11 and Android 4.3-, which do not recognize the ``<main>`` element, to treat is as a block-level component.

### Accessibility

- Default underlines and outlines are removed from hyperlinks. 
- Focus identifiers are removed from all interactive elements.
- All interactive elements, except disabled ones, when hovered over will show the pointer cursor.
- Where the ``accesskey`` attribute is used, it is automatically rendered in the element's ``::after`` pseudo element.

### Miscellany

- Margins and padding are removed from all elements globally.
- The vertical scrollbar is kept visible, even on pages with no vertical overflow. 
- Custom scrollbars are implemented in WebKit browsers.
- There are polyfills for IE's proprietary ``unselectable`` attribute, for the ``hidden`` attribute, and a partial polyfill for the ``<template>`` element.


## Browsers

Elementary CSS has been tested in the following browsers. The figures in brackets are [global market share as of July 2017](http://gs.statcounter.com/).

- Android 4.4 (1%)
- Chrome 58-60 for Windows, macOS and Ubuntu (22%)
- Chrome 60 for Android (30%)
- Edge 40 (1%)
- Firefox 54 for Windows, macOS and Ubuntu (3.75%)
- Internet Explorer 11 (3%)
- Opera 47 (1%)
- Opera Mini 28 for Android (~3%)
- Safari 10.1 for macOS (1.3%)
- Safari 10.2 (1.5%) and 10.3 (8%) for iOS 
- Samsung Internet for Android 4 (3.8%)
- UC Browser for Android 11.4 (9.1%)


## Credits

Elementary CSS is authored and maintained by [Kieran Potts](https://www.kieranpotts.com/). It builds on the great work of other open source software projects, notably:

- [Eric Meyer's Reset CSS](http://meyerweb.com/eric/tools/css/reset/)
- [HTML5 Doctor Reset Stylesheet](http://html5doctor.com/html-5-reset-stylesheet/)
- [HTML5 Reset](http://html5reset.org/)
- [normalize.css](http://necolas.github.io/normalize.css/)
- [YUI CSS Reset](http://yuilibrary.com/yui/docs/cssreset/)
- [sanitize.css](http://jonathantneal.github.io/sanitize.css/)
- [marx](https://github.com/mblode/marx)


## Contributing

This is a free and open source software project. It is made possible by generous contributions from software engineers, both expert and novice, from around the world. There are three ways that you can get involved:

- Request features
- Report bugs
- Iterate the source code

All contributions – bug reports, feature requests, and material changes to the source code – are managed via the project's [issue tracker](https://github.com/kieranpotts/elementary/issues).

### Feature requests

Feature requests are welcome. Feature requests may be submitted via the [issue tracker](https://github.com/kieranpotts/elementary/issues). Please add the "enhancement" label and prefix the title "Idea:".

Take a moment to consider whether your idea fits with the scope and aims of the project, and what are the benefits versus costs of adding the feature.

### Bug reports

Before reporting a bug, please check that it has not already been reported previously by searching the [issue tracker](https://github.com/kieranpotts/elementary/issues). Also check that the problem has not already been fixed by trying to reproduce the problem in the ``master`` branch.

To fix an error, the software maintainers must be able to reproduce it. This requires you to be able to demonstrate the bug. A good bug report will therefore include at least one of the following:

- Detailed step-by-step instructions to reproduce the error.
- A live example of the problem, e.g. a [Codepen](http://codepen.io/).
- A reduced test case, like the ones in our ``./tests/`` directory.

Please provide details of the browser name, version number, and operating system in which you experienced the error. Describe the outcome your expected, and what's different about the actual outcome.

If you can identify the source of the bug, such as a specific line or block of code, please include this information in your bug report, too.

### Source changes

The ultimate way to contribute to any open source software project is to help makes changes to its source code, tests, and documentation. This is done using the pull request (PR) system. 

Please raise an issue before making a pull request. The project maintainers will review your bug report or feature request, and they will accept or reject it before you spend time implementing the fix or enhancement.

The fork-and-branch workflow is used to manage changes to the project's source code. This allows individual contributors to work in isolation without interfering with anyone else's work.

The steps are as follows:

#### 1. Fork

From the project's GitHub page, click "Fork". The project's repository will be cloned in your own GitHub account. The fork is your "origin" repository, while the main project repository is referred to as the "upstream" repository.

#### 2. Clone

Download a copy of your origin repository:

```
git clone https://github.com/<your-github-username>/elementary.git
```

The copy of the project that now exists on your computer is your "local" repository. This is where you'll do your work. 

When you run the ``git clone`` command, Git automatically adds a remote named "origin", which you will push back to when you've made changes in your local repository. You should add another remote that references the upstream repository. From the root directory of your newly cloned local repository, run the following command in your terminal:

```
git remote add upstream https://github.com/kieranpotts/elementary.git
```

#### 3. Checkout

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

#### 4. Branch

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

#### 5. Stage and commit

Undertake your work in your issue branch.

If you are making substantive changes over a long period, you should make regular commits, organizing your changes in logical iterations. Long-lived feature branches should be kept synchronized with the project mainline, and you may like to backup your work by pushing regularly to your origin repository on GitHub. See below for instructions.

Be sure to add or update the relevant reduced test cases, which are in the ``./tests`` directory. The reduced test cases are plain HTML documents that demonstrate the effect of the Elementary CSS style sheet on isolated HTML elements.

Make your changes, and stage and commit them. Using the ``-a`` flag on commit will allow you to submit a commit subject plus a more detailed body message, if you wish.

```
git add
git commit -a
```

#### 6. Synchronize

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

#### 7. Push

Push the changes your local issue branch to your remote origin repository. Because rebasing changes history, you should use ``-f`` or ``--force`` to force changes into the remote.

```
git push -f origin issue/21-improve-pre-line-height
```

If someone else is working on the same branch, use the less destructive ``--force-with-lease``.


#### 8. Pull request

Now all your work is in your origin repository, which is attached to your GitHub user account. From the GitHub page for your origin repository, issue a [pull request](https://help.github.com/articles/about-pull-requests/) to have your work merged in to the project's upstream repository. Click the "Pull Request" button on GitHub and follow the steps. Provide a clear title and description, and be sure to leave checked the option to "allow edits from maintainers". 

The maintainers of the upstream repository will review and merge your changes into the project.

_By opening a pull request, you agree to allow the project maintainers to license your work under the same terms as the project._

#### 9. Tidy up

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
- Use a dedicated commit to bump the version number. The commit message must be in the format ``v1.0.0``. Use the commit description to list functional changes. The same information should be added to the CHANGELOG which can be updated in the same commit.
- Create an annotated tag on ``master`` for the release: ``git tag -m "v1.0.0" 1.0.0``.
- Push the changes and tags: ``git push --tags origin master``.
- Update the  website by checking out the ``gh-pages`` branch and following the instructions in the README in that branch.

### Semantic versioning

[Semver](http://semver.org/) is the gold standard for software version numbering. Version numbers are written as ``v<major>.<minor>.<patch>``, e.g. ``v1.0.5``.

_Any_ change to _any_ CSS selector or rule will break backwards compatibility. Therefore, all CSS changes will increment the major version number. Comments and formatting changes will bump the patch number. There is no type of change that can be made to CSS that is considered to be minor.

### Standards

Elementary CSS is compatible with modern web standards. No effort is made to deal with HTML elements that have been deprecated from the HTML5 specification, things like ``<acronym>`` and ``<center>``. New HTML elements that have been recently added to the specification but which are not yet widely supported, things like ``<menu>``, are also omitted.

### Compatibility

Once a browser release dips below 1% global market share _in the browser's category_, the minimum supported version is bumped. Note that category share is higher than total market share. For example, Microsoft Edge has about a 1% total market share, but more than 3% in the desktop category and higher still among Windows users.


## License

The MIT License (MIT)

Copyright (c) 2017 Kieran Potts

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
