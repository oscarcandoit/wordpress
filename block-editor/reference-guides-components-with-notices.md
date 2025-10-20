---
url: https://developer.wordpress.org/block-editor/reference-guides/components/with-notices
scraped_at: 2025-10-20T03:21:37.396Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/with-notices/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

WithNotices


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)WithNotices

Search

# WithNotices

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/with-notices/#wp--skip-link--target)

`withNotices` is a React [higher-order component](https://facebook.github.io/react/docs/higher-order-components.html) used typically in adding the ability to post notice messages within the original component.

Wrapping the original component with `withNotices` encapsulates the component with the additional props `noticeOperations`, `noticeUI`, and `noticeList`.

**noticeOperations**

Contains a number of useful functions to add notices to your site.

[#](https://developer.wordpress.org/block-editor/reference-guides/components/with-notices/#createNotice) **createNotice**

Function passed down as a prop that adds a new notice.

_Parameters_

- _notice_ `object`: Notice to add.

[#](https://developer.wordpress.org/block-editor/reference-guides/components/with-notices/#createErrorNotice) **createErrorNotice**

Function passed as a prop that adds a new error notice.

_Parameters_

- _msg_ `string`: Error message of the notice.

[#](https://developer.wordpress.org/block-editor/reference-guides/components/with-notices/#removeAllNotices) **removeAllNotices**

Function that removes all notices.

[#](https://developer.wordpress.org/block-editor/reference-guides/components/with-notices/#removeNotice) **removeNotice**

Function that removes notice by ID.

_Parameters_

- _id_ `string`: ID of notice to remove.

[#](https://developer.wordpress.org/block-editor/reference-guides/components/with-notices/#noticeUi) **noticeUi**

The rendered `NoticeList`.

[#](https://developer.wordpress.org/block-editor/reference-guides/components/with-notices/#noticeList) **noticeList**

The array of notice objects to be displayed.

## Usage

```jsx
import { withNotices, Button } from '@wordpress/components';

const MyComponentWithNotices = withNotices(
    ( { noticeOperations, noticeUI } ) => {
        const addError = () =>
            noticeOperations.createErrorNotice( 'Error message' );
        return (
            <div>
                { noticeUI }
                <Button variant="secondary" onClick={ addError }>
                    Add error
                </Button>
            </div>
        );
    }
);

```

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: WithNotices](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/higher-order/with-notices/README.md)

[PreviousWithFocusReturnPrevious: WithFocusReturn](https://developer.wordpress.org/block-editor/reference-guides/components/with-focus-return/)

[NextWithSpokenMessagesNext: WithSpokenMessages](https://developer.wordpress.org/block-editor/reference-guides/components/with-spoken-messages/)

Notifications