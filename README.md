# Elementary CSS

Elementary CSS is an aggressive reset style sheet.

The principal purpose of a reset style sheet is to iron out inconsistencies in the default presentation given to HTML elements by web browsers. Elementary CSS goes further, overridding the browser's default style sheet to provide a more practical baseline from which to compose modern web application interfaces.


## Installation

Elementary CSS is not intended to be used as is. You are encouraged to fork and modify Elementary CSS for your own needs. You should change the fonts and colours and create your own set of base styles that are appropriate for your application's GUI.

Download the contents of the ``./src/`` directory and incorporate them into your project. You will need a Sass tool to compile ``./src/elementary.scss`` to CSS. Alternatively, you can use the pre-compiled ``./build/elementary.css`` or ``./build/elementary.min.css``.


## Features

As well as fixing common cross-browser inconsistencies, Elementary CSS implements the following changes to the browser's default styles.

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
- Only the ``<b>`` and ``<strong>`` elements are rendered with bold text, and only the ``<em>`` and ``<i>`` elements are italicized. Every other element, including ``<cite>`` and ``<address>``, is rendered in the normal font style. Many other default text decorations are removed, such as underlines from ``<u>`` and ``<del>`` and the default background highlight of ``<mark>``.
- The ``<small>`` element now adopts the ``font-size`` of its parent, turning this into a purely semantic element (it means "small print"). The ``<address>`` element also has been redefined as a sectioning element yet most browsers still treat it as a text node, italicizing its text content. This has been fixed.
- Generated quotes are removed from ``<blockquote>`` and ``<q>``. 
- The default implementation of ``<sup>`` and ``<sub>`` affects line height in all browsers. Elementary CSS implements a better methodology to render superscript and subscript text, one which does not bork line height.
- Where the non-standard ``text-rendering`` property is supported, it is set to ``optimizeLegibility``.

### Tables

- The default border model for tables is changed from ``separated`` to ``collapsed``, which is more convenient for styling. 
- Tables cells are configured to adjust their width automatically to best fit their content. 

### Multimedia

- Images and multimedia containers such as ``<video>`` are converted from inline to block-level display, and are made responsive by default.
- The ``<video>`` element is also made to never exceed the width of its container, and is given a dark background colour so that scaled-down videos are nicely letterboxed. 
- ``<audio>`` elements are not rendered if they don't have playback controls enabled.
- Embedded SVGs are configured to inherit the color of adjacent text as their default ``fill`` color. This is a handy hack for inline icons.

### Forms

- Form elements such as ``<label>``, ``<input>``, and ``<button>``, also have their default ``display`` property changed to ``block``, since they are commonly used as block-level elements.
- The defult border put around ``<fieldset>`` elements is removed.
- Placeholder text is given a consistent color across all browsers.

### Structure

- The modern clearfix hack is applied to sectioning elements such as ``<article>`` and ``<section>``, so these containers will always clear any floated elements nested inside them.
- The ``<address>`` element has been reclassified by the W3C as a sectioning element, so the legacy application of italics to text content is undone.
- There's a fix in place for IE 11 and Android 4.3-, which do not recognize the ``<main>`` element, to treat is as a block-level component.

### Accessibility

- Default underlines and outlines are removed from hyperlinks. 
- Focus identifiers are removed from all interactive elements.
- All interactive elements, except disabled ones, when hovered over will show the pointer cursor.
- Where the ``accesskey`` attribute is used, it is automatically rendered in the element's ``::after`` pseudo element.

### Miscellany

- Margins and padding are removed from all elements globally.
- The vertical scrollbar is kept visible, even on pages with no vertical overflow. Custom scrollbars are implemented in WebKit browsers.
- There are polyfills for IE's proprietary ``unselectable`` attribute, for the ``hidden`` attribute, and a partial polyfill for the new ``<template>`` element.

Elementary CSS is compatible with modern web standards. No effort is made to deal with HTML elements that have been deprecated from the HTML5 specification, things like ``<acronym>`` and ``<center>``. New HTML elements that have been recently added to the specification but which are not yet widely supported, things like ``<menu>``, are also omitted.


## Browsers

Elementary CSS has been tested in the following browsers. The figures in brackets are [global market share as of July 2017](http://gs.statcounter.com/).

- Android 4.4 (1%)
- Chrome 58-60 for Windows, macOS and Ubuntu (22%)
- Chrome latest for Android (30%)
- Edge 40 (1%)
- Firefox 54 for Windows, macOS and Ubuntu (3.75%)
- Internet Explorer 11 (3%)
- Opera latest (1%)
- Opera Mini latest (3.3%)
- Safari 10.1 for macOS (1.3%)
- Safari 10.2 (1.5%) and 10.3 (8%) for iOS 
- Samsung Internet for Android 4 (3.8%)
- UC Browser for Android 11.4 (9.1%)

Once a browser release dips below 1% global market share _in the browser's category_, the minimum supported version is bumped. Note that category share is higher than total market share. For example, Microsoft Edge has about a 1% total market share, but more than 3% in the desktop category and higher still among Windows users.


## Contributing

To get involved in this project, or to submit bug reports and feature requests, please use the [issue tracker](https://github.com/kieranpotts/elementary/issues). 


## Credits

Elementary CSS is authored and maintained by [Kieran Potts](https://www.kieranpotts.com/). It builds on the great work of other open source software projects, notably:

- [Eric Meyer's Reset CSS](http://meyerweb.com/eric/tools/css/reset/)
- [HTML5 Doctor Reset Stylesheet](http://html5doctor.com/html-5-reset-stylesheet/)
- [HTML5 Reset](http://html5reset.org/)
- [normalize.css](http://necolas.github.io/normalize.css/)
- [YUI CSS Reset](http://yuilibrary.com/yui/docs/cssreset/)
- [sanitize.css](http://jonathantneal.github.io/sanitize.css/)
- [marx](https://github.com/mblode/marx)


## License

The MIT License (MIT)

Copyright (c) 2017 Kieran Potts

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
