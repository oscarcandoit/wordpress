---
url: https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json
scraped_at: 2025-10-20T03:13:25.500Z
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

theme.json


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)[Curating the Editor Experience](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/)theme.json

Search

# theme.json

## In this article

Table of Contents

- [Providing default controls/options](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/#providing-default-controls-options)
- [Limiting interface options with theme.json](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/#limiting-interface-options-with-theme-json)
  - [Limit options on a per-block basis](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/#limit-options-on-a-per-block-basis)
  - [Disable inherit default layout](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/#disable-inherit-default-layout)
  - [Limit options globally](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/#limit-options-globally)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/#wp--skip-link--target)

A theme’s theme.json file is one of the best ways to curate the Editor experience and will likely be the first tool you use before reaching for more sophisticated solutions.

## [Providing default controls/options](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/\#providing-default-controls-options)

Since theme.json acts as a configuration tool, there are numerous ways to define at a granular level what options are available. This section will use duotone as an example since it showcases a feature that cuts across a few blocks and allows for varying levels of access.

_Duotone with Core options and customization available for each image related block:_

```json
{
    "version": 3,
    "settings": {
        "color": {
            "customDuotone": true,
            "duotone": [\
            ]
        }
    }
}

```

_Duotone with theme defined color options, Core options, and customization available for each image related block:_

```json
{
    "version": 3,
    "settings": {
        "color": {
            "duotone": [\
                {\
                    "colors": [ "#000000", "#ffffff" ],\
                    "slug": "foreground-and-background",\
                    "name": "Foreground and background"\
                },\
                {\
                    "colors": [ "#000000", "#ff0200" ],\
                    "slug": "foreground-and-secondary",\
                    "name": "Foreground and secondary"\
                },\
                {\
                    "colors": [ "#000000", "#7f5dee" ],\
                    "slug": "foreground-and-tertiary",\
                    "name": "Foreground and tertiary"\
                },\
            ]
        }
    }
}

```

_Duotone with defined default options and all customization available for the Post Featured Image block:_

```json
{
    "version": 3,
    "settings": {
        "color": {
            "custom": true,
            "customDuotone": true
        },
        "blocks": {
            "core/post-featured-image": {
                "color": {
                    "duotone": [\
                        {\
                            "colors": [ "#282828", "#ff5837" ],\
                            "slug": "black-and-orange",\
                            "name": "Black and Orange"\
                        },\
                        {\
                            "colors": [ "#282828", "#0288d1" ],\
                            "slug": "black-and-blue",\
                            "name": "Black and Blue"\
                        }\
                    ],
                    "customDuotone": true,
                    "custom": true
                }
            }
        }
    }
}

```

_Duotone with only defined default options and core options available for the Post Featured Image block (no customization):_

```json
{
    "version": 3,
    "settings": {
        "color": {
            "custom": true,
            "customDuotone": true
        },
        "blocks": {
            "core/post-featured-image": {
                "color": {
                    "duotone": [\
                        {\
                            "colors": [ "#282828", "#ff5837" ],\
                            "slug": "black-and-orange",\
                            "name": "Black and Orange"\
                        },\
                        {\
                            "colors": [ "#282828", "#0288d1" ],\
                            "slug": "black-and-blue",\
                            "name": "Black and Blue"\
                        }\
                    ],
                    "customDuotone": false,
                    "custom": false
                }
            }
        }
    }
}

```

## [Limiting interface options with theme.json](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/\#limiting-interface-options-with-theme-json)

### [Limit options on a per-block basis](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/\#limit-options-on-a-per-block-basis)

Beyond defining default values, using theme.json allows you to also remove options entirely and instead rely on what the theme has set in place. Below is a visual showing two extremes with the same paragraph block:

![Image of restricted interface](https://i0.wp.com/raw.githubusercontent.com/WordPress/gutenberg/HEAD/docs/assets/Locking%20comparison%20visual.png?ssl=1)

Continuing the examples with duotone, this means you could allow full access to all Duotone functionality for Image blocks and only limit the Post Featured Image block like so:

```json
{
    "version": 3,
    "settings": {
        "color": {
            "custom": true,
            "customDuotone": true
        },
        "blocks": {
            "core/image": {
                "color": {
                    "duotone": [],
                    "customDuotone": true,
                    "custom": true
                }
            },
            "core/post-featured-image": {
                "color": {
                    "duotone": [],
                    "customDuotone": false,
                    "custom": false
                }
            }
        }
    }
}

```

You can read more about how best to [turn on/off options with theme.json here](https://developer.wordpress.org/block-editor/how-to-guides/themes/global-settings-and-styles/).

### [Disable inherit default layout](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/\#disable-inherit-default-layout)

To disable the “Inherit default layout” setting for container blocks like the Group block, remove the following section:

```json
"layout": {
    "contentSize": null,
    "wideSize": null
},

```

### [Limit options globally](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/theme-json/\#limit-options-globally)

When using theme.json in a block or classic theme, these settings will stop the default color and typography controls from being enabled globally, greatly limiting what’s possible:

```json
{
    "version": 3,
    "settings": {
        "layout": {
            "contentSize": "750px"
        },
        "color": {
            "background": false,
            "custom": false,
            "customDuotone": false,
            "customGradient": false,
            "defaultGradients": false,
            "defaultPalette": false,
            "text": false
        },
        "typography": {
            "customFontSize": false,
            "dropCap": false,
            "fontStyle": false,
            "fontWeight": false,
            "letterSpacing": false,
            "lineHeight": false,
            "textDecoration": false,
            "textTransform": false
        }
    }
}

```

To enable something from the above, just set whatever value you want to change to `true` for more granularity.

First published

April 26, 2021

Last updated

April 30, 2024

Edit article

[Improve it on GitHub: theme.json](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/curating-the-editor-experience/theme-json.md)

[PreviousPatternsPrevious: Patterns](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/patterns/)

[NextFilters and hooksNext: Filters and hooks](https://developer.wordpress.org/block-editor/how-to-guides/curating-the-editor-experience/filters-and-hooks/)

Notifications