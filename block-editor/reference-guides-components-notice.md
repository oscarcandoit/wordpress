---
url: https://developer.wordpress.org/block-editor/reference-guides/components/notice
scraped_at: 2025-10-20T03:19:17.924Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Notice


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Notice

Search

# Notice

## In this article

Table of Contents

- [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#design-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#usage)
  - [Do’s and Don’ts](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#dos-and-donts)
- [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#development-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#usage-2)
  - [Props](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#props)
- [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#related-components)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/notice/#wp--skip-link--target)

Use Notices to communicate prominent messages to the user.

![Notice component](https://i0.wp.com/make.wordpress.org/design/files/2019/03/Notice-Screenshot-alt.png?ssl=1)

## [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#design-guidelines)

A Notice displays a succinct message. It can also offer the user options, like viewing a published post or updating a setting, and requires a user action to be dismissed.

Use Notices to communicate things that are important but don’t necessarily require action — a user can keep using the product even if they don’t choose to act on a Notice. They are less interruptive than a Modal.

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#usage)

Notices display at the top of the screen, below any toolbars anchored to the top of the page. They’re persistent and non-modal. Since they don’t overlay the content, users can ignore or dismiss them, and choose when to interact with them.

Notices are color-coded to indicate the type of message being communicated:

- **Informational** notices are **blue** by default.
- If there is a parent `Theme` component with an `accent` color prop, informational notices will take on that color instead.
- **Success** notices are **green.**
- **Warning** notices are **yellow.**
- **Error** notices are **red.**

If an icon is included in the Notice, it should be color-coded to match the Notice state.

### [Do’s and Don’ts](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#dos-and-donts)

**Do** use a Notice when you want to communicate a message of medium importance.

![A success Notice for updating a post](https://i0.wp.com/make.wordpress.org/design/files/2019/03/Notice-Do-1-alt.png?ssl=1)

* * *

**Don’t** use a Notice for a message that requires immediate attention and action from the user. Use a Modal for this instead.

![A Notice that requires an immediate action](https://i0.wp.com/make.wordpress.org/design/files/2019/03/Notice-Dont-1-alt.png?ssl=1)

* * *

**Do** display Notices at the top of the screen, below any toolbars.

![A success Notice for publishing a post](https://i0.wp.com/make.wordpress.org/design/files/2019/03/Notice-Do-2-alt.png?ssl=1)

* * *

**Don’t** show Notices on top of toolbars.

![A success Notice on top of the editor toolbar](https://i0.wp.com/make.wordpress.org/design/files/2019/03/Notice-Dont-2-alt.png?ssl=1)

* * *

**Do** use color to indicate the type of message being communicated.

![An error Notice using red](https://i0.wp.com/make.wordpress.org/design/files/2019/03/Notice-Do-3-alt.png?ssl=1)

* * *

**Don’t** apply any colors other than those for Warnings, Success, or Errors.

![An error Notice using purple](https://i0.wp.com/make.wordpress.org/design/files/2019/03/Notice-Dont-3-alt.png?ssl=1)

## [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#development-guidelines)

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#usage-2)

To display a plain notice, pass `Notice` a string:

```jsx
import { Notice } from '@wordpress/components';

const MyNotice = () => (
    <Notice status="error">An unknown error occurred.</Notice>
);

```

For more complex markup, you can pass any JSX element:

```jsx
import { Notice } from '@wordpress/components';

const MyNotice = () => (
    <Notice status="error">
        <p>
            An error occurred: <code>{ errorDetails }</code>.
        </p>
    </Notice>
);

```

### [Props](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#props)

The following props are used to control the behavior of the component.

#### [children: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#children-reactnode)

The displayed message of a notice. Also used as the spoken message for assistive technology, unless `spokenMessage` is provided as an alternative message.

- Required: Yes

#### [spokenMessage: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#spokenmessage-reactnode)

Used to provide a custom spoken message in place of the `children` default.

- Required: No
- Default: `children`

#### [status: ‘warning’ \| ‘success’ \| ‘error’ \| ‘info’](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#status-warning-success-error-info)

Determines the color of the notice: `warning` (yellow), `success` (green), `error` (red), or `'info'`. By default `'info'` will be blue, but if there is a parent Theme component with an accent color prop, the notice will take on that color instead.

- Required: No
- Default: `info`

#### [onRemove: () => void](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#onremove-void)

A function called to dismiss/remove the notice.

- Required: No
- Default: `noop`

#### [politeness: ‘polite’ \| ‘assertive’](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#politeness-polite-assertive)

A politeness level for the notice’s spoken message. Should be provided as one of the valid options for [an `aria-live` attribute value](https://www.w3.org/TR/wai-aria-1.1/#aria-live).

- A value of `'assertive'` is to be used for important, and usually time-sensitive, information. It will interrupt anything else the screen reader is announcing in that moment.
- A value of `'polite'` is to be used for advisory information. It should not interrupt what the screen reader is announcing in that moment (the “speech queue”) or interrupt the current task.

Note that this value should be considered a suggestion; assistive technologies may override it based on internal heuristics.

- Required: No
- Default: `'assertive'` or `'polite'`, based on the notice status.

#### [isDismissible: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#isdismissible-boolean)

Whether the notice should be dismissible or not

- Required: No
- Default: `true`

#### [onDismiss : () => void](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#ondismiss-void)

A deprecated alternative to `onRemove`. This prop is kept for compatibility reasons but should be avoided.

- Required: No
- Default: `noop`

#### [actions: Array<NoticeAction>.](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#actions-arraynoticeaction)

An array of notice actions. Each member object should contain:

- `label`: `string` containing the text of the button/link
- `url`: `string` OR `onClick`: `( event: SyntheticEvent ) => void` to specify what the action does.
- `openInNewTab`: `boolean` (optional) When set to `true`, opens the URL in a new browser tab.
- `className`: `string` (optional) to add custom classes to the button styles.
- `noDefaultClasses`: `boolean` (optional) A value of `true` will remove all default styling.
- `variant`: `'primary' | 'secondary' | 'link'` (optional) You can denote a primary button action for a notice by passing a value of `primary`.

The default appearance of an action button is inferred based on whether `url` or `onClick` are provided, rendering the button as a link if appropriate. If both props are provided, `url` takes precedence, and the action button will render as an anchor tag.

## [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/notice/\#related-components)

- To create a more prominent message that requires action, use a Modal.
- For low priority, non-interruptive messages, use Snackbar.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Notice](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/notice/README.md)

[PreviousNavigatorPrevious: Navigator](https://developer.wordpress.org/block-editor/reference-guides/components/navigator/)

[NextNumberControlNext: NumberControl](https://developer.wordpress.org/block-editor/reference-guides/components/number-control/)

Notifications