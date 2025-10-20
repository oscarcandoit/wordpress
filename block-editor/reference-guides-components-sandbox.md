---
url: https://developer.wordpress.org/block-editor/reference-guides/components/sandbox
scraped_at: 2025-10-20T03:24:05.595Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Sandbox


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Sandbox

Search

# Sandbox

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#props)
  - [html: string](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#html-string)
  - [onFocus: React.DOMAttributes< HTMLIFrameElement >\[ ‘onFocus’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#onfocus-react-domattributes-htmliframeelement-onfocus)
  - [scripts: string\[\]](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#scripts-string)
  - [styles: string\[\]](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#styles-string)
  - [title: string](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#title-string)
  - [type: string](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#type-string)
  - [tabIndex: HTMLElement\[ ‘tabIndex’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#tabindex-htmlelement-tabindex)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/#wp--skip-link--target)

This component provides an isolated environment for arbitrary HTML via iframes.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#usage)

```jsx
import { SandBox } from '@wordpress/components';

const MySandBox = () => (
    <SandBox html="<p>Content</p>" title="SandBox" type="embed" />
);

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#props)

### [html: string](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#html-string)

The HTML to render in the body of the iframe document.

- Required: No
- Default: “”

### [onFocus: React.DOMAttributes< HTMLIFrameElement >\[ ‘onFocus’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#onfocus-react-domattributes-htmliframeelement-onfocus)

The `onFocus` callback for the iframe.

- Required: No

### [scripts: string\[\]](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#scripts-string)

An array of script URLs to inject as `<script>` tags into the bottom of the `<body>` of the iframe document.

- Required: No
- Default: \[\]

### [styles: string\[\]](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#styles-string)

An array of CSS strings to inject into the `<head>` of the iframe document.

- Required: No
- Default: \[\]

### [title: string](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#title-string)

The `<title>` of the iframe document.

- Required: No
- Default: “”

### [type: string](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#type-string)

The CSS class name to apply to the `<html>` and `<body>` elements of the iframe.

- Required: No
- Default: “”

### [tabIndex: HTMLElement\[ ‘tabIndex’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/sandbox/\#tabindex-htmlelement-tabindex)

The `tabindex` the iframe should receive.

- Required: No

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Sandbox](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/sandbox/README.md)

[PreviousResponsiveWrapperPrevious: ResponsiveWrapper](https://developer.wordpress.org/block-editor/reference-guides/components/responsive-wrapper/)

[NextScrollLockNext: ScrollLock](https://developer.wordpress.org/block-editor/reference-guides/components/scroll-lock/)

Notifications