---
url: https://developer.wordpress.org/block-editor/reference-guides/components/placeholder
scraped_at: 2025-10-20T03:19:45.880Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Placeholder


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Placeholder

Search

# Placeholder

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#props)
  - [className: string](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#classname-string)
  - [icon: string\|Function\|Component\|null](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#icon-stringfunctioncomponentnull)
  - [instructions: string](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#instructions-string)
  - [isColumnLayout: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#iscolumnlayout-boolean)
  - [label: string](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#label-string)
  - [notices: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#notices-reactnode)
  - [preview: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#preview-reactnode)
  - [withIllustration: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#withillustration-boolean)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/#wp--skip-link--target)

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#usage)

```jsx
import { Placeholder } from '@wordpress/components';
import { more } from '@wordpress/icons';

const MyPlaceholder = () => <Placeholder icon={ more } label="Placeholder" />;

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#props)

### [className: string](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#classname-string)

Class to set on the container div.

- Required: No

### [icon: string\|Function\|Component\|null](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#icon-stringfunctioncomponentnull)

If provided, renders an icon next to the label.

- Required: No

### [instructions: string](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#instructions-string)

Instructions of the placeholder.

- Required: No

### [isColumnLayout: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#iscolumnlayout-boolean)

Changes placeholder children layout from flex-row to flex-column.

- Required: No

### [label: string](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#label-string)

Title of the placeholder.

- Required: No

### [notices: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#notices-reactnode)

A rendered notices list

- Required: No

### [preview: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#preview-reactnode)

Preview to be rendered in the placeholder.

- Required: No

### [withIllustration: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/placeholder/\#withillustration-boolean)

Outputs a placeholder illustration.

- Required: No

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Placeholder](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/placeholder/README.md)

[PreviousPanelPrevious: Panel](https://developer.wordpress.org/block-editor/reference-guides/components/panel/)

[NextPopoverNext: Popover](https://developer.wordpress.org/block-editor/reference-guides/components/popover/)

Notifications