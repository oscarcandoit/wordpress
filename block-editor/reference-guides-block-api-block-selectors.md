---
url: https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors
scraped_at: 2025-10-20T03:13:34.676Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Selectors


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Block API Reference](https://developer.wordpress.org/block-editor/reference-guides/block-api/)Selectors

Search

# Selectors

## In this article

Table of Contents

- [Root selector](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#root-selector)
  - [Example](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#example)
- [Feature selectors](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#feature-selectors)
  - [Example](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#example-2)
- [Subfeature selectors](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#subfeature-selectors)
  - [Example](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#example-3)
- [Shorthand](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#shorthand)
- [Fallbacks](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#fallbacks)
  - [Example](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#example-4)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/#wp--skip-link--target)

Block Selectors is the API that allows blocks to customize the CSS selector used

when their styles are generated.

A block may customize its CSS selectors at three levels: root, feature, and

subfeature.

## [Root selector](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#root-selector)

The root selector is the block’s primary CSS selector.

All blocks require a primary CSS selector for their style declarations to be

included under. If one is not provided through the Block Selectors API, a

default is generated in the form of `.wp-block-<name>`.

### [Example](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#example)

```json
{
    ...
    "selectors": {
        "root": ".my-custom-block-selector"
    }
}

```

## [Feature selectors](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#feature-selectors)

Feature selectors relate to styles for a block support, e.g. border, color,

typography, etc.

A block may wish to apply the styles for specific features to different

elements within a block. An example might be using colors on the block’s wrapper

but applying the typography styles to an inner heading only.

### [Example](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#example-2)

```json
{
    ...
    "selectors": {
        "root": ".my-custom-block-selector",
        "color": ".my-custom-block-selector",
        "typography": ".my-custom-block-selector > h2"
    }
}

```

## [Subfeature selectors](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#subfeature-selectors)

These selectors relate to individual styles provided by a block support e.g.

`background-color`

A subfeature can have styles generated under its own unique selector. This is

especially useful where one block support subfeature can’t be applied to the

same element as the support’s other subfeatures.

A great example of this is `text-decoration`. Web browsers render this style

differently, making it difficult to override if added to a wrapper element. By

assigning `text-decoration` a custom selector, its style can target only the

elements to which it should be applied.

### [Example](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#example-3)

```json
{
    ...
    "selectors": {
        "root": ".my-custom-block-selector",
        "color": ".my-custom-block-selector",
        "typography": {
            "root": ".my-custom-block-selector > h2",
            "text-decoration": ".my-custom-block-selector > h2 span"
        }
    }
}

```

## [Shorthand](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#shorthand)

Rather than specify a CSS selector for every subfeature, you can set a single

selector as a string value for the relevant feature. This is the approach

demonstrated for the `color` feature in the earlier examples above.

## [Fallbacks](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#fallbacks)

A selector that hasn’t been configured for a specific feature will fall back to

the block’s root selector. Similarly, if a subfeature hasn’t had a custom

selector set, it will fall back to its parent feature’s selector and, if unavailable, fall back further to the block’s root selector.

Rather than repeating selectors for multiple subfeatures, you can set the

common selector as the parent feature’s `root` selector and only define the

unique selectors for the subfeatures that differ.

### [Example](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-selectors/\#example-4)

```json
{
    ...
    "selectors": {
        "root": ".my-custom-block-selector",
        "color": {
            "text": ".my-custom-block-selector p"
        },
        "typography": {
            "root": ".my-custom-block-selector > h2",
            "text-decoration": ".my-custom-block-selector > h2 span"
        }
    }
}

```

The `color.background-color` subfeature isn’t explicitly set in the above

example. As the `color` feature also doesn’t define a `root` selector,

`color.background-color` would be included under the block’s primary root

selector, `.my-custom-block-selector`.

For a subfeature such as `typography.font-size`, it would fallback to its parent

feature’s selector given that is present, i.e. `.my-custom-block-selector > h2`.

First published

April 13, 2023

Last updated

October 30, 2024

Edit article

[Improve it on GitHub: Selectors](https://github.com/WordPress/gutenberg/edit/trunk/docs/reference-guides/block-api/block-selectors.md)

[PreviousRegistrationPrevious: Registration](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-registration/)

[NextStylesNext: Styles](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-styles/)

Notifications