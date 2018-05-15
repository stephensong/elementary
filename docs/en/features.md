# Features


Elementary CSS fixes bugs and cross-browser inconsistencies in the default presentation of HTML elements. In addition, Elementary CSS implements the following extensions to the browser's default style sheet.


## Typography

- The default font is set to Roboto. 
- Inconsolata, a monospace font, is adopted for ``<pre>``, ``<code>``, ``<kbd>``, ``<samp>``, and ``<var>``.
- The root font size is changed from 16px to 10px, making it easier to specify relative sizes using root em (``rem``) units.
- The default font size is 1.2rem (1.2 x 10 = 12px). This is the size that text is rendered on mobile devices. On larger screens, the root font size is bumped up, meaning that anything sized in rem units will automatically scale proportionally to the size of the rendering window. This is a simple implementation of basic mobile-first responsiveness.
- The default font color is changed to ``hsl(0, 0%, 10%)``, which is equivalent to the hex ``#1A1A1A``. 
- Properties such as ``color``, ``font-family`` and ``font-weight`` are made to be inherited by all elements, including ``<textarea>`` and ``<legend>``, which traditionally have not inherited these properties.
- The ``line-height`` of all block-level text is set to 1x its ``font-size``.
- Bullets are removed from unordered lists (``<ul>``), but numbering is persisted on ordered lists (``<ol>``) so that the useful ``type`` attribute still works: ``<ol type="A">``. 
- Only the ``<b>`` and ``<strong>`` elements are rendered with bold text, and only the ``<em>`` and ``<i>`` elements are italicized. Every other element, including ``<cite>`` and ``<address>``, is rendered in the normal font style. 
- Many other default text decorations are removed, such as underlines from ``<u>`` and ``<del>``, the background color from ``<mark>``, and generated quotes from ``<blockquote>`` and ``<q>``. 
- The ``<small>`` element now adopts the ``font-size`` of its parent, turning this into a purely semantic tag.
- A consistent default presentation for the horizontal rule element (``<hr>``) is applied across all browsers. 
- A better methodology to render superscript (``<sup>``) and subscript (``<sub>``) text is adopted, one which does not have side effects on line height.


## Tables

- The default border model for tables is changed from ``separated`` to ``collapsed``, which is more convenient for styling. 
- Tables cells are configured to adjust their width automatically to best fit their content. 


## Multimedia

- Images and multimedia containers such as ``<video>`` are converted from inline to block-level display, and are made responsive by default.
- The ``<video>`` element is given a dark background color so that scaled-down videos are nicely letterboxed. 
- ``<audio>`` elements are not rendered if they don't have playback controls enabled.
- Embedded SVGs are configured to inherit the color of adjacent text as their default ``fill``. This is a handy hack for inline icons.


## Forms

- Form elements such as ``<label>``, ``<input>``, and ``<button>`` are changed from inline to block-level display, since they are commonly used as such.
- The border around ``<fieldset>`` containers is removed.
- Placeholder text is given a consistent color across all browsers.


## Structure

- The modern clearfix hack is applied to sectioning elements such as ``<header>`` and ``<article>``, so these containers will always clear any nested floated content.
- The ``<address>`` element has been reclassified as a sectioning element, the legacy application of italics to text content within this element is removed.


## Accessibility

- The browser's default underlines and outlines are removed from hyperlinks, and focus identifiers are removed from everything. The reason for this change is that CSS authors commonly implement custom solutions for these accessibility requirements.
- The ``<abbr>`` and ``<dfn>`` elements are differentiated from normal text only if they have a ``title`` attribute.
- All interactive elements when hovered over will show the pointer cursor, except when disabled.
- Where the ``accesskey`` attribute is used, its value is rendered in the element's ``::after`` pseudo element.


## Miscellany

- Margins and padding are removed from all elements globally.
- The vertical scrollbar is kept visible, even on pages with no vertical overflow.
- Custom scrollbars are implemented in WebKit browsers.
- There are polyfills for IE's proprietary ``unselectable`` attribute, for the ``hidden`` attribute, the ``<main>`` element, and a partial polyfill for the ``<template>`` element.
