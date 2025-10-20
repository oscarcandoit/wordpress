---
url: https://developer.wordpress.org/block-editor/how-to-guides/feature-flags
scraped_at: 2025-10-20T03:17:15.060Z
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Feature Flags


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)Feature Flags

Search

# Feature Flags

## In this article

Table of Contents

- [Introducing globalThis.IS\_GUTENBERG\_PLUGIN](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#introducing-globalthis-is_gutenberg_plugin)
- [Basic usage](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#basic-usage)
  - [Exporting features](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#exporting-features)
  - [Importing features](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#importing-features)
- [How it works](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#how-it-works)
  - [Dead code elimination](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#dead-code-elimination)
- [Frequently asked questions](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#frequently-asked-questions)
  - [Why shouldn’t I assign the result of an expression involving IS\_GUTENBERG\_PLUGIN to a variable, e.g. const isMyFeatureActive = ! Object.is( undefined, globalThis.IS\_GUTENBERG\_PLUGIN )?](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#why-shouldnt-i-assign-the-result-of-an-expression-involving-is_gutenberg_plugin-to-a-variable-e-g-const-ismyfeatureactive-object-is-undefined-globalthis-is_gutenberg_plugin)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#wp--skip-link--target)

‘Feature flags’ are variables that allow you to prevent specific code in the Gutenberg project from being shipped to WordPress core, and to run certain experimental features only in the plugin.

## [Introducing globalThis.IS\_GUTENBERG\_PLUGIN](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/\#introducing-globalthis-is_gutenberg_plugin)

The `globalThis.IS_GUTENBERG_PLUGIN` is an environment variable whose value ‘flags’ whether code is running within the Gutenberg plugin.

When the codebase is built for the plugin, this variable will be set to `true`. When building for WordPress core, it will be set to `false` or `undefined`.

## [Basic usage](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/\#basic-usage)

### [Exporting features](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/\#exporting-features)

A plugin-only function or constant should be exported using the following ternary syntax:

```js
function myPluginOnlyFeature() {
    // implementation
}

export const pluginOnlyFeature = globalThis.IS_GUTENBERG_PLUGIN
    ? myPluginOnlyFeature
    : undefined;

```

In the above example, the `pluginOnlyFeature` export will be `undefined` in non-plugin environments such as WordPress core.

### [Importing features](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/\#importing-features)

If you’re attempting to import and call a plugin-only feature, be sure to wrap the function call in an `if` statement to avoid an error:

```js
import { pluginOnlyFeature } from '@wordpress/foo';

if ( globalThis.IS_GUTENBERG_PLUGIN ) {
    pluginOnlyFeature();
}

```

## [How it works](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/\#how-it-works)

During the webpack build, instances of `globalThis.IS_GUTENBERG_PLUGIN` will be replaced using webpack’s [define plugin](https://webpack.js.org/plugins/define-plugin/).

For example, in the following code –

```js
if ( globalThis.IS_GUTENBERG_PLUGIN ) {
    pluginOnlyFeature();
}

```

– the variable `globalThis.IS_GUTENBERG_PLUGIN` will be replaced with the boolean `true` during the plugin-only build:

```js
if ( true ) {
    // Webpack has replaced `globalThis.IS_GUTENBERG_PLUGIN` with `true`
    pluginOnlyFeature();
}

```

This ensures that code within the body of the `if` statement will always be executed.

In WordPress core, the `globalThis.IS_GUTENBERG_PLUGIN` variable is replaced with `undefined`. The built code looks like this:

```js
if ( undefined ) {
    // Webpack has replaced `globalThis.IS_GUTENBERG_PLUGIN` with `undefined`
    pluginOnlyFeature();
}

```

`undefined` evaluates to `false` so the plugin-only feature will not be executed.

### [Dead code elimination](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/\#dead-code-elimination)

For production builds, webpack [‘minifies’](https://en.wikipedia.org/wiki/Minification_(programming)) the code, removing as much unnecessary JavaScript as it can.

One of the steps involves something known as ‘dead code elimination’. For example, when the following code is encountered, webpack determines that the surrounding `if` statement is unnecessary:

```js
if ( true ) {
    pluginOnlyFeature();
}

```

The condition will always evaluate to `true`, so webpack removes it, leaving behind the code that was in the body:

```js
pluginOnlyFeature(); // The `if` condition block has been removed. Only the body remains.

```

Similarly, when building for WordPress core, the condition in the following `if` statement always resolves to false:

```js
if ( undefined ) {
    pluginOnlyFeature();
}

```

In this case, the minification process will remove the entire `if` statement including the body, ensuring plugin-only code is not included in WordPress core build.

## [Frequently asked questions](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/\#frequently-asked-questions)

### [Why shouldn’t I assign the result of an expression involving IS\_GUTENBERG\_PLUGIN to a variable, e.g. const isMyFeatureActive = ! Object.is( undefined, globalThis.IS\_GUTENBERG\_PLUGIN )?](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/\#why-shouldnt-i-assign-the-result-of-an-expression-involving-is_gutenberg_plugin-to-a-variable-e-g-const-ismyfeatureactive-object-is-undefined-globalthis-is_gutenberg_plugin)

Introducing complexity may prevent webpack’s minifier from identifying and therefore eliminating dead code. Therefore it is recommended to use the examples in this document to ensure your feature flag functions as intended. For further details, see the [Dead Code Elimination](https://developer.wordpress.org/block-editor/how-to-guides/feature-flags/#dead-code-elimination) section.

First published

March 9, 2021

Last updated

January 11, 2025

Edit article

[Improve it on GitHub: Feature Flags](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/feature-flags.md)

[PreviousEnqueueing assets in the EditorPrevious: Enqueueing assets in the Editor](https://developer.wordpress.org/block-editor/how-to-guides/enqueueing-assets-in-the-editor/)

[NextFormatting Toolbar APINext: Formatting Toolbar API](https://developer.wordpress.org/block-editor/how-to-guides/format-api/)

Notifications