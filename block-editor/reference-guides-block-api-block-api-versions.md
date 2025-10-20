---
url: https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions
scraped_at: 2025-10-20T03:14:07.955Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

API Versions


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Block API Reference](https://developer.wordpress.org/block-editor/reference-guides/block-api/)API Versions

Search

# API Versions

## In this article

Table of Contents

- [Version 3 (>= WordPress 6.3)](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions/#version-3-wordpress-6-3)
- [Version 2 (>= WordPress 5.6)](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions/#version-2-wordpress-5-6)
- [Version 1](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions/#version-1)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions/#wp--skip-link--target)

This document lists the changes made between the different API versions.

## [Version 3 (>= WordPress 6.3)](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions/\#version-3-wordpress-6-3)

- The post editor will be iframed if all registered blocks have a Block API version 3 or higher. Adding version 3 support means that the block should work inside an iframe, though the block may still be rendered outside the iframe if not all blocks support version 3.
- See [this article](https://make.wordpress.org/core/2021/06/29/blocks-in-an-iframed-template-editor/) for a migration guide to bump the API version to 3 and make them work in an iframe editor.

## [Version 2 (>= WordPress 5.6)](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions/\#version-2-wordpress-5-6)

- To render the block element wrapper for the block’s `edit` implementation, the block author must use the `useBlockProps()` hook.
- The generated class names and styles are no longer added automatically to the saved markup for static blocks when `save` is processed. To include them, the block author must explicitly use `useBlockProps.save()` and add to their block wrapper.

## [Version 1](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-api-versions/\#version-1)

Initial version.

First published

April 21, 2021

Last updated

August 4, 2025

Edit article

[Improve it on GitHub: API Versions](https://github.com/WordPress/gutenberg/edit/trunk/docs/reference-guides/block-api/block-api-versions.md)

[PreviousAnnotationsPrevious: Annotations](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-annotations/)

[NextAttributesNext: Attributes](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-attributes/)

Notifications