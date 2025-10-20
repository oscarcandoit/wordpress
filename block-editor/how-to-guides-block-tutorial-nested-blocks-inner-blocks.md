---
url: https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks
scraped_at: 2025-10-20T03:13:15.764Z
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Nested Blocks: Using InnerBlocks


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)[Blocks](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/)Nested Blocks: Using InnerBlocks

Search

# Nested Blocks: Using InnerBlocks

## In this article

Table of Contents

- [Allowed blocks](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#allowed-blocks)
- [Orientation](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#orientation)
- [Default block](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#default-block)
- [Template](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#template)
  - [Post template](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#post-template)
- [Using parent, ancestor and children relationships in blocks](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#using-parent-ancestor-and-children-relationships-in-blocks)
  - [Defining parent block relationship](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#defining-parent-block-relationship)
  - [Defining an ancestor block relationship](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#defining-an-ancestor-block-relationship)
  - [Defining a children block relationship](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#defining-a-children-block-relationship)
- [Using a React hook](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#using-a-react-hook)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#wp--skip-link--target)

You can create a single block that nests other blocks using the [InnerBlocks](https://github.com/WordPress/gutenberg/tree/HEAD/packages/block-editor/src/components/inner-blocks/README.md) component. This is used in the Columns block, Social Links block, or any block you want to contain other blocks.

Note: A single block can only contain one `InnerBlocks` component.

Here is the basic InnerBlocks usage.

```js
import { registerBlockType } from '@wordpress/blocks';
import { InnerBlocks, useBlockProps } from '@wordpress/block-editor';

registerBlockType( 'gutenberg-examples/example-06', {
    // ...

    edit: () => {
        const blockProps = useBlockProps();

        return (
            <div { ...blockProps }>
                <InnerBlocks />
            </div>
        );
    },

    save: () => {
        const blockProps = useBlockProps.save();

        return (
            <div { ...blockProps }>
                <InnerBlocks.Content />
            </div>
        );
    },
} );

```

## [Allowed blocks](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#allowed-blocks)

Using the `allowedBlocks` prop, you can further limit, in addition to the `allowedBlocks` field in `block.json`, which blocks can be inserted as direct descendants of this block. It is useful to determine the list of allowed blocks dynamically, individually for each block. For example, determined by a block attribute:

```js
const { allowedBlocks } = attributes;
//...
<InnerBlocks allowedBlocks={ allowedBlocks } />;

```

If the list of allowed blocks is always the same, prefer the [`allowedBlocks` block setting](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/#defining-a-children-block-relationship) instead.

## [Orientation](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#orientation)

By default, `InnerBlocks` expects its blocks to be shown in a vertical list. A valid use-case is to style inner blocks to appear horizontally, for instance by adding CSS flex or grid properties to the inner blocks wrapper. When blocks are styled in such a way, the `orientation` prop can be set to indicate that a horizontal layout is being used:

```js
<InnerBlocks orientation="horizontal" />

```

Specifying this prop does not affect the layout of the inner blocks, but results in the block mover icons in the child blocks being displayed horizontally, and also ensures that drag and drop works correctly.

## [Default block](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#default-block)

By default `InnerBlocks` opens a list of permitted blocks via `allowedBlocks` when the block appender is clicked. You can modify the default block and its attributes that are inserted when the initial block appender is clicked by using the `defaultBlock` property. For example:

```js
<InnerBlocks defaultBlock={['core/paragraph', {placeholder: "Lorem ipsum..."}]} directInsert />

```

By default this behavior is disabled until the `directInsert` prop is set to `true`. This allows you to specify conditions for when the default block should or should not be inserted.

## [Template](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#template)

Use the template property to define a set of blocks that prefill the InnerBlocks component when it has no existing content.. You can set attributes on the blocks to define their use. The example below shows a book review template using InnerBlocks component and setting placeholders values to show the block usage.

```js
const MY_TEMPLATE = [\
    [ 'core/image', {} ],\
    [ 'core/heading', { placeholder: 'Book Title' } ],\
    [ 'core/paragraph', { placeholder: 'Summary' } ],\
];

//...

    edit: () => {
        return (
            <InnerBlocks
                template={ MY_TEMPLATE }
                templateLock="all"
            />
        );
    },

```

Use the `templateLock` property to lock down the template. Using `all` locks the template completely so no changes can be made. Using `insert` prevents additional blocks from being inserted, but existing blocks can be reordered. See [templateLock documentation](https://github.com/WordPress/gutenberg/tree/HEAD/packages/block-editor/src/components/inner-blocks/README.md#templatelock) for additional information.

### [Post template](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#post-template)

Unrelated to `InnerBlocks` but worth mentioning here, you can create a [post template](https://developer.wordpress.org/block-editor/developers/block-api/block-templates/) by post type, that preloads the block editor with a set of blocks.

The `InnerBlocks` template is for the component in the single block that you created, the rest of the post can include any blocks the user likes. Using a post template, can lock the entire post to just the template you define.

```php
add_action( 'init', function() {
    $post_type_object = get_post_type_object( 'post' );
    $post_type_object->template = array(
        array( 'core/image' ),
        array( 'core/heading' )
    );
} );

```

## [Using parent, ancestor and children relationships in blocks](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#using-parent-ancestor-and-children-relationships-in-blocks)

A common pattern for using InnerBlocks is to create a custom block that will only be available if its parent block is inserted. This allows builders to establish a relationship between blocks, while limiting a nested block’s discoverability. There are three relationships that builders can use: `parent`, `ancestor` and `allowedBlocks`. The differences are:

- If you assign a `parent` then you’re stating that the nested block can only be used and inserted as a **direct descendant of the parent**.
- If you assign an `ancestor` then you’re stating that the nested block can only be used and inserted as a **descendent of the parent**.
- If you assign the `allowedBlocks` then you’re stating a relationship in the opposite direction, i.e., which blocks can be used and inserted as **direct descendants of this block**.

The key difference between `parent` and `ancestor` is `parent` has finer specificity, while an `ancestor` has greater flexibility in its nested hierarchy.

### [Defining parent block relationship](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#defining-parent-block-relationship)

An example of this is the Column block, which is assigned the `parent` block setting. This allows the Column block to only be available as a nested direct descendant in its parent Columns block. Otherwise, the Column block will not be available as an option within the block inserter. See [Column code for reference](https://github.com/WordPress/gutenberg/tree/HEAD/packages/block-library/src/column).

When defining a direct descendent block, use the `parent` block setting to define which block is the parent. This prevents the nested block from showing in the inserter outside of the InnerBlock it is defined for.

```json
{
    "title": "Column",
    "name": "core/column",
    "parent": [ "core/columns" ],
    // ...
}

```

### [Defining an ancestor block relationship](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#defining-an-ancestor-block-relationship)

An example of this is the Comment Author Name block, which is assigned the `ancestor` block setting. This allows the Comment Author Name block to only be available as a nested descendant in its ancestral Comment Template block. Otherwise, the Comment Author Name block will not be available as an option within the block inserter. See [Comment Author Name code for reference](https://github.com/WordPress/gutenberg/tree/HEAD/packages/block-library/src/comment-author-name).

The `ancestor` relationship allows the Comment Author Name block to be anywhere in the hierarchical tree, and not _just_ a direct child of the parent Comment Template block, while still limiting its availability within the block inserter to only be visible an an option to insert if the Comment Template block is available.

When defining a descendent block, use the `ancestor` block setting. This prevents the nested block from showing in the inserter outside of the InnerBlock it is defined for.

```json
{
    "title": "Comment Author Name",
    "name": "core/comment-author-name",
    "ancestor": [ "core/comment-template" ],
    // ...
}

```

### [Defining a children block relationship](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#defining-a-children-block-relationship)

An example of this is the Navigation block, which is assigned the `allowedBlocks` block setting. This makes only a certain subset of block types to be available as direct descendants of the Navigation block. See [Navigation code for reference](https://github.com/WordPress/gutenberg/tree/HEAD/packages/block-library/src/navigation).

The `allowedBlocks` setting can be extended by builders of custom blocks. The custom block can hook into the `blocks.registerBlockType` filter and add itself to the available children of the Navigation.

When defining a set of possible descendant blocks, use the `allowedBlocks` block setting. This limits what blocks are showing in the inserter when inserting a new child block.

```json
{
    "title": "Navigation",
    "name": "core/navigation",
    "allowedBlocks": [ "core/navigation-link", "core/search", "core/social-links", "core/page-list", "core/spacer" ],
    // ...
}

```

## [Using a React hook](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/nested-blocks-inner-blocks/\#using-a-react-hook)

You can use a react hook called `useInnerBlocksProps` instead of the `InnerBlocks` component. This hook allows you to take more control over the markup of inner blocks areas.

The `useInnerBlocksProps` is exported from the `@wordpress/block-editor` package same as the `InnerBlocks` component itself and supports everything the component does. It also works like the `useBlockProps` hook.

It is important to note that `useBlockProps` hook must be called _before_ `useInnerBlocksProps`, otherwise `useBlockProps` will return empty object.

Here is the basic `useInnerBlocksProps` hook usage.

```js
import { registerBlockType } from '@wordpress/blocks';
import { useBlockProps, useInnerBlocksProps } from '@wordpress/block-editor';

registerBlockType( 'gutenberg-examples/example-06', {
    // ...

    edit: () => {
        const blockProps = useBlockProps();
        const innerBlocksProps = useInnerBlocksProps();

        return (
            <div { ...blockProps }>
                <div {...innerBlocksProps} />
            </div>
        );
    },

    save: () => {
        const blockProps = useBlockProps.save();
        const innerBlocksProps = useInnerBlocksProps.save();

        return (
            <div { ...blockProps }>
                <div {...innerBlocksProps} />
            </div>
        );
    },
} );

```

This hook can also pass objects returned from the `useBlockProps` hook to the `useInnerBlocksProps` hook. This reduces the number of elements we need to create.

```js
import { registerBlockType } from '@wordpress/blocks';
import { useBlockProps, useInnerBlocksProps } from '@wordpress/block-editor';

registerBlockType( 'gutenberg-examples/example-06', {
    // ...

    edit: () => {
        const blockProps = useBlockProps();
        const innerBlocksProps = useInnerBlocksProps( blockProps );

        return (
            <div {...innerBlocksProps} />
        );
    },

    save: () => {
        const blockProps = useBlockProps.save();
        const innerBlocksProps = useInnerBlocksProps.save( blockProps );

        return (
            <div {...innerBlocksProps} />
        );
    },
} );

```

The above code will render to the following markup in the editor:

```html
<div>
    <!-- Inner Blocks get inserted here -->
</div>

```

Another benefit to using the hook approach is using the returned value, which is just an object, and deconstruct to get the react children from the object. This property contains the actual child inner blocks thus we can place elements on the same level as our inner blocks.

```js
import { registerBlockType } from '@wordpress/blocks';
import { useBlockProps, useInnerBlocksProps } from '@wordpress/block-editor';

registerBlockType( 'gutenberg-examples/example-06', {
    // ...

    edit: () => {
        const blockProps = useBlockProps();
        const { children, ...innerBlocksProps } = useInnerBlocksProps( blockProps );

        return (
            <div {...innerBlocksProps}>
                { children }
                <!-- Insert any arbitrary html here at the same level as the children -->
            </div>
        );
    },

    // ...
} );

```

```html
<div>
    <!-- Inner Blocks get inserted here -->
    <!-- The custom html gets rendered on the same level -->
</div>

```

First published

March 9, 2021

Last updated

July 2, 2025

Edit article

[Improve it on GitHub: Nested Blocks: Using InnerBlocks](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/block-tutorial/nested-blocks-inner-blocks.md)

[PreviousCreating dynamic blocksPrevious: Creating dynamic blocks](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/creating-dynamic-blocks/)

[NextExtending the Query Loop blockNext: Extending the Query Loop block](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/extending-the-query-loop-block/)

Notifications