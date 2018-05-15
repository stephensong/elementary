# Changelog
All notable changes to this project will be documented in this file. The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [v2.0.0] - 2018-05-15
- Fix used of ampersand in nested selectors for abbreviations, definitions, and quotes.
- Include standard syntax for ``appearance`` and ``text-size-adjust`` properties where vendor-prefixed versions used.
- Rename ``build`` directory as ``dist``.
- Include ``dist`` directory in version control.
- Rename ``tests`` directory as ``demo``. Use minified CSS for demos.

## [v1.0.0] - 2017-08-20
- Removed margins and padding globally.
- Minimum page width set to 320px.
- Always show vertical scrollbar.
- Embedded Roboto and Inconsolata fonts in WOFF and WOFF2 formats.
- Monospace font applied to ``<code>``, ``<kbd>``, ``<pre>``, ``<samp>`` and ``<var>``.
- ``font-family``, ``font-weight`` and ``color`` inherited universally.
- ``font-style`` and ``font-weight`` removed from all elements except ``<em>``, ``<i>``, ``<strong>`` and ``<b>``.
- Root ``font-size`` changed from 16px to 10px for easier root em (``rem``) calculations.
- Root font size increases slightly on larger screens, mobile-first responsive design.
- ``line-height`` matched ``font-size`` universally.
- Non-standard ``text-rendering`` property set to ``optimizeLegibility``.
- Non-standard ``text-size-adjust`` set to 100%.
- Default text color: ``hsl(0, 0%, 10%)``.
- Placeholder text: ``hsl(0, 0%, 70%)``.
- Embedded SVGs inherit ``fill`` from parent ``color`` setting.
- Bullets removed from ``<ul>``.
- Numbering persisted on ``<ol>``.
- Cross-browser consistent implementation of ``<hr>``.
- Wrap text in ``<figure>`` and ``<pre>`` blocks.
- Suppress line wrapping in ``<code>``.
- Remove dotted underline from ``<abbr>`` and ``<dfn>``.
- Remove generated quotes from ``<blockquote>`` and ``<q>``.
- No default ``text-decoration`` for ``<del>``, ``<ins>``, ``<u>`` and ``<s>``.
- Remove background highlight from ``<mark>``.
- Alternative implementation of ``<sub>`` and ``<sup>`` does not affect line height.
- ``<small>`` rendered at 100% ``font-size`` of parent.
- Better default presentation for selected text (``::selection``).
- Border model for tables changed from separated to collapsed.
- Tables fill 100% width of container.
- Table cells adjust their width automatically for content best-fit.
- Borders, backgrounds and other properties cascade through table structures.
- Remove default underlines from hyperlinks.
- Remove outlines and other focus identifiers from all interactive elements.
- All controls, except disabled ones, show pointer cursor on hover.
- Print ``accesskey`` attribute value in ``::after`` pseudo element.
- Convert ``<label>``, ``<button>``, ``<input>``, ``<select>`` and ``<textarea>`` to block-level display.
- Remove default backgrounds and borders from buttons and inputs.
- Change buttons and inputs to ``border-box`` box sizing model.
- Minimum height for textareas: 10em.
- ``<img>``, ``<video>``, ``<audio>``, ``<iframe>``, ``<object>``, ``<embed>``, ``<canvas>`` and ``<svg>`` rendered block-level.
- Images and other multimedia containers made responsive by default.
- ``<audio>`` elements not shown if playback controls disabled.
- ``<meter>`` and ``<progress>`` elements set to ``inline-block`` display for better consistency in incompatible clients.
- IE 11 and Android 4.3- made to recognise ``<main>`` element and render block-level.
- Polyfills for IE's proprietary ``unselectable`` attribute, for the ``hidden`` attribute, and the ``<template>`` element.
- Modern clearfix hack applied to all sectioning elements plus ``<figure>``, ``<form>`` and ``<fieldset>``.
- Simple custom scrollbar design for WebKit browsers.
- Various well-documented cross-browser rendering inconsistencies fixed.
