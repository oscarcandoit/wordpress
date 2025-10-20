---
url: https://developer.wordpress.org/block-editor/reference-guides/filters/autocomplete-filters
scraped_at: 2025-10-20T03:17:28.564Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/filters/autocomplete-filters/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Autocomplete


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Hooks Reference](https://developer.wordpress.org/block-editor/reference-guides/filters/)Autocomplete

Search

# Autocomplete

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/filters/autocomplete-filters/#wp--skip-link--target)

The `editor.Autocomplete.completers` filter is for extending and overriding the list of autocompleters used by blocks.

The `Autocomplete` component found in `@wordpress/block-editor` applies this filter. The `@wordpress/components` package provides the foundational `Autocomplete` component that does not apply such a filter, but blocks should generally use the component provided by `@wordpress/block-editor`.

### Example

Here is an example of using the `editor.Autocomplete.completers` filter to add an acronym completer. You can find full documentation for the autocompleter interface with the `Autocomplete` component in the `@wordpress/components` package.

```jsx
// Our completer
const acronymCompleter = {
    name: 'acronyms',
    triggerPrefix: '::',
    options: [\
        { letters: 'FYI', expansion: 'For Your Information' },\
        { letters: 'AFAIK', expansion: 'As Far As I Know' },\
        { letters: 'IIRC', expansion: 'If I Recall Correctly' },\
    ],
    getOptionKeywords( { letters, expansion } ) {
        const expansionWords = expansion.split( /\s+/ );
        return [ letters, ...expansionWords ];
    },
    getOptionLabel: acronym => acronym.letters,
    getOptionCompletion: ( { letters, expansion } ) => (
        <abbr title={ expansion }>{ letters }</abbr>,
    ),
};

// Our filter function
function appendAcronymCompleter( completers, blockName ) {
    return blockName === 'my-plugin/foo' ?
        [ ...completers, acronymCompleter ] :
        completers;
}

// Adding the filter
wp.hooks.addFilter(
    'editor.Autocomplete.completers',
    'my-plugin/autocompleters/acronym',
    appendAcronymCompleter
);

```

First published

March 9, 2021

Last updated

October 30, 2024

Edit article

[Improve it on GitHub: Autocomplete](https://github.com/WordPress/gutenberg/edit/trunk/docs/reference-guides/filters/autocomplete-filters.md)

[PreviousParser FiltersPrevious: Parser Filters](https://developer.wordpress.org/block-editor/reference-guides/filters/parser-filters/)

[NextGlobal Styles FiltersNext: Global Styles Filters](https://developer.wordpress.org/block-editor/reference-guides/filters/global-styles-filters/)

Notifications