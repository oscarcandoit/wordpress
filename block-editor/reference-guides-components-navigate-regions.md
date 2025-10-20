---
url: https://developer.wordpress.org/block-editor/reference-guides/components/navigate-regions
scraped_at: 2025-10-20T03:21:52.082Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/navigate-regions/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

NavigateRegions


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)NavigateRegions

Search

# NavigateRegions

## In this article

Table of Contents

- [Example:](https://developer.wordpress.org/block-editor/reference-guides/components/navigate-regions/#example)
- [Notes:](https://developer.wordpress.org/block-editor/reference-guides/components/navigate-regions/#notes)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/navigate-regions/#wp--skip-link--target)

`navigateRegions` is a React [higher-order component](https://facebook.github.io/react/docs/higher-order-components.html) adding keyboard navigation to switch between the different DOM elements marked as “regions” (role=”region”). These regions should be focusable (By adding a tabIndex attribute for example). For better accessibility, these elements must be properly labelled to briefly describe the purpose of the content in the region. For more details, see “Landmark Roles” in the [WAI-ARIA specification](https://www.w3.org/TR/wai-aria/) and “Landmark Regions” in the [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/practices/landmark-regions/).

## [Example:](https://developer.wordpress.org/block-editor/reference-guides/components/navigate-regions/\#example)

```jsx
import { navigateRegions } from '@wordpress/components';

const MyComponentWithNavigateRegions = navigateRegions( () => (
    <div>
        <div role="region" tabIndex="-1" aria-label="Header">
            Header
        </div>
        <div role="region" tabIndex="-1" aria-label="Content">
            Content
        </div>
        <div role="region" tabIndex="-1" aria-label="Sidebar">
            Sidebar
        </div>
    </div>
) );

```

## [Notes:](https://developer.wordpress.org/block-editor/reference-guides/components/navigate-regions/\#notes)

It’s important to note that an ARIA `role="region"` is an ARIA landmark role. It should be reserved for sections of content sufficiently important to have it listed in a summary of the page. Only use this ARIA role for the main sections of a page. All perceivable content should reside in a semantically meaningful landmark in order that content is not missed by the user.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: NavigateRegions](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/higher-order/navigate-regions/README.md)

[PreviousHeadingPrevious: Heading](https://developer.wordpress.org/block-editor/reference-guides/components/heading/)

[NextHigherOrderNext: HigherOrder](https://developer.wordpress.org/block-editor/reference-guides/components/higher-order/)

Notifications