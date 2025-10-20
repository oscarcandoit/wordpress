---
url: https://developer.wordpress.org/block-editor/reference-guides/components/guide
scraped_at: 2025-10-20T03:21:32.017Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Guide


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Guide

Search

# Guide

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#props)
  - [className](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#classname)
  - [contentLabel](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#contentlabel)
  - [finishButtonText](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#finishbuttontext)
  - [nextButtonText](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#nextbuttontext)
  - [previousButtonText](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#previousbuttontext)
  - [onFinish](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#onfinish)
  - [pages](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#pages)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/guide/#wp--skip-link--target)

`Guide` is a React component that renders a _user guide_ in a modal. The guide consists of several pages which the user can step through one by one. The guide is finished when the modal is closed or when the user clicks _Finish_ on the last page of the guide.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#usage)

```jsx
function MyTutorial() {
    const [ isOpen, setIsOpen ] = useState( true );

    if ( ! isOpen ) {
        return null;
    }

    return (
        <Guide
            onFinish={ () => setIsOpen( false ) }
            pages={ [\
                {\
                    content: <p>Welcome to the ACME Store!</p>,\
                },\
                {\
                    image: <img src="https://acmestore.com/add-to-cart.png" />,\
                    content: (\
                        <p>\
                            Click <i>Add to Cart</i> to buy a product.\
                        </p>\
                    ),\
                },\
            ] }
        />
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#props)

The component accepts the following props:

### [className](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#classname)

A custom class to add to the modal.

- Type: `string`
- Required: No

### [contentLabel](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#contentlabel)

This property is used as the modal’s accessibility label. It is required for accessibility reasons.

- Type: `string`
- Required: Yes

### [finishButtonText](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#finishbuttontext)

Use this to customize the label of the _Finish_ button shown at the end of the guide.

- Type: `string`
- Required: No
- Default: `'Finish'`

### [nextButtonText](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#nextbuttontext)

Use this to customize the label of the _Next_ button shown on each page of the guide.

- Type: `string`
- Required: No
- Default: `'Next'`

### [previousButtonText](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#previousbuttontext)

Use this to customize the label of the _Previous_ button shown on each page of the guide except the first.

- Type: `string`
- Required: No
- Default: `'Previous'`

### [onFinish](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#onfinish)

A function which is called when the guide is finished. The guide is finished when the modal is closed or when the user clicks _Finish_ on the last page of the guide.

- Type: `( event?: KeyboardEvent< HTMLDivElement > | SyntheticEvent ) => void`
- Required: Yes

### [pages](https://developer.wordpress.org/block-editor/reference-guides/components/guide/\#pages)

A list of objects describing each page in the guide. Each object **must** contain a `'content'` property and may optionally contain a `'image'` property.

- Type: `{ content: ReactNode; image?: ReactNode; }[]`
- Required: No
- Default: `[]`

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Guide](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/guide/README.md)

[PreviousGridPrevious: Grid](https://developer.wordpress.org/block-editor/reference-guides/components/grid/)

[NextHStackNext: HStack](https://developer.wordpress.org/block-editor/reference-guides/components/h-stack/)

Notifications