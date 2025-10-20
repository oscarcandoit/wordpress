---
url: https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar
scraped_at: 2025-10-20T03:23:29.828Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

ProgressBar


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)ProgressBar

Search

# ProgressBar

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/#usage)
  - [Props](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/#props)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/#wp--skip-link--target)

A simple horizontal progress bar component.

Supports two modes: determinate and indeterminate. A progress bar is determinate when a specific progress value has been specified (from 0 to 100), and indeterminate when a value hasn’t been specified.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/\#usage)

Basic usage:

```jsx
import { ProgressBar } from '@wordpress/components';

const MyLoadingComponent = () => {
    return <ProgressBar />;
};

```

You can also make it determinate by passing a `value` (from 0 to 100) representing the progress:

```jsx
import { ProgressBar } from '@wordpress/components';

const MyLoadingComponent = ( { progress } ) => {
    return <ProgressBar value={ progress } />;
};

```

You can customize its appearance by passing a custom CSS class name to `className`.

```css
.my-custom-progress-bar {
    width: 100%;
}

```

```jsx
import { ProgressBar } from '@wordpress/components';

const MyLoadingComponent = () => {
    return <ProgressBar className="my-custom-progress-bar" />;
};

```

### [Props](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/\#props)

The component accepts the following props:

#### [value: number](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/\#value-number)

The progress value, a number from 0 to 100.

If a `value` is not specified, the progress bar will be considered indeterminate.

- Required: No

#### [className: string](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/\#classname-string)

A CSS class to apply to the underlying `div` element, serving as a progress bar track.

- Required: No

#### [Inherited props](https://developer.wordpress.org/block-editor/reference-guides/components/progress-bar/\#inherited-props)

Any additional props will be passed the underlying `<progress/>` element.

First published

May 29, 2024

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: ProgressBar](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/progress-bar/README.md)

[PreviousPopoverPrevious: Popover](https://developer.wordpress.org/block-editor/reference-guides/components/popover/)

[NextQueryControlsNext: QueryControls](https://developer.wordpress.org/block-editor/reference-guides/components/query-controls/)

Notifications