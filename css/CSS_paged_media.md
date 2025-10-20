---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media
scraped_at: 2025-10-20T03:05:29.655Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media#search)

# CSS paged media

The **CSS paged media** module defines the properties that control the presentation of content for print or any other media that splits content into discrete pages. It allows you to set page breaks, control printable areas, and style left and right pages differently.

The CSS paged media module specifies how pages are generated and laid out to hold fragmented content in a paged presentation, including content that is printed or represented as a print preview. The module defines functionality for controlling page margins, size, orientation, and headers and footers. It extends [generated content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content) to provide functionality for generating page numbers and running headers and footers.

The process of paginating content into generated pages and controlling breaks inside elements is covered in the [CSS fragmentation module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fragmentation).

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media\#properties)

- [`page`](https://developer.mozilla.org/en-US/docs/Web/CSS/page)

### [At-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media\#at-rules)

- [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page)
  - [`page-orientation`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page/page-orientation) descriptor
  - [`size`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page/size) descriptor
  - [Margin descriptors](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
- [Margin at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/@page#margin_at-rules)

The CSS paged media module also introduces the `bleeds` and `marks` descriptors of the `@page` at-rule. Currently, no browsers support these features.

### [Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media\#pseudo-classes)

- [`:blank`](https://developer.mozilla.org/en-US/docs/Web/CSS/:blank)
- [`:first`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first)
- [`:left`](https://developer.mozilla.org/en-US/docs/Web/CSS/:left)
- [`:right`](https://developer.mozilla.org/en-US/docs/Web/CSS/:right)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media\#guides)

[Printing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Printing)

Tips and techniques for helping improve web content printer output.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media\#related_concepts)

- [CSS fragmentation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fragmentation) module

  - [`break-after`](https://developer.mozilla.org/en-US/docs/Web/CSS/break-after) property
  - [`break-before`](https://developer.mozilla.org/en-US/docs/Web/CSS/break-before) property
  - [`break-inside`](https://developer.mozilla.org/en-US/docs/Web/CSS/break-inside) property
  - [`orphans`](https://developer.mozilla.org/en-US/docs/Web/CSS/orphans) property
  - [`widows`](https://developer.mozilla.org/en-US/docs/Web/CSS/widows) property

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media\#specifications)

| Specification |
| --- |
| [CSS Paged Media Module Level 3](https://drafts.csswg.org/css-page/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media\#see_also)

- [CSS fragmentation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fragmentation) module
- [CSS media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Sep 3, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_paged_media/index.md?plain=1 "Folder: ⁨en-us/web/css/css_paged_media⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_paged_media&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_paged_media%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_paged_media%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_paged_media%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F6948f64c02c25f3200bef45f69b9560eead391f8%0A*+Document+last+modified%3A+2025-09-03T10%3A24%3A38.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")