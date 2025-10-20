---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/cursor
scraped_at: 2025-10-20T03:04:26.265Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# cursor


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨December 2021⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcursor&level=high)

The **`cursor`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the mouse cursor, if any, to show when the mouse pointer is over an element.

The cursor setting should inform users of the mouse operations that can be performed at the current location, including: text selection, activating help or context menus, copying content, resizing tables, and so on.
You can specify either the _type_ of cursor using a keyword, or load a specific icon to use (with optional fallback images and mandatory keyword as a final fallback).

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#try_it)

- cursor: help;

- cursor: wait;

- cursor: crosshair;

- cursor: not-allowed;

- cursor: zoom-in;

- cursor: grab;


cssCopy

```
cursor: help;

```

cssCopy

```
cursor: wait;

```

cssCopy

```
cursor: crosshair;

```

cssCopy

```
cursor: not-allowed;

```

cssCopy

```
cursor: zoom-in;

```

cssCopy

```
cursor: grab;

```

htmlCopy

```
<section class="default-example container" id="default-example">
  <div id="example-element">
    Move over this element to see the cursor style.
  </div>
</section>

```

cssCopy

```
#example-element {
  display: flex;
  background-color: #1766aa;
  color: white;
  height: 180px;
  width: 360px;
  justify-content: center;
  align-items: center;
  font-size: 14pt;
  padding: 5px;
}

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#syntax)

cssCopy

```
/* Keyword value */
cursor: auto;
cursor: pointer;
/* … */
cursor: zoom-out;

/* URL with mandatory keyword fallback */
cursor: url("hand.cur"), pointer;

/* URL and coordinates, with mandatory keyword fallback */
cursor:
  url("cursor_1.png") 4 12,
  auto;
cursor:
  url("cursor_2.png") 2 2,
  pointer;

/* URLs and fallback URLs (some with coordinates), with mandatory keyword fallback */
cursor:
  url("cursor_1.svg") 4 5,
  url("cursor_2.svg"),
  /* …, */ url("cursor_n.cur") 5 5,
  progress;

/* Global values */
cursor: inherit;
cursor: initial;
cursor: revert;
cursor: revert-layer;
cursor: unset;

```

The `cursor` property is specified as zero or more `<url>` values, separated by commas, followed by a single mandatory keyword value.
Each `<url>` should point to an image file.
The browser will try to load the first image specified, falling back to the next if it can't, and falling back to the keyword value if no images could be loaded (or if none were specified).

Each `<url>` may be optionally followed by a pair of space-separated numbers, which set the `<x>` and `<y>` coordinates of the cursor's hotspot relative to the top-left corner of the image.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#values)

[`<url>` Optional](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor#url)

A `url()` or a comma separated list `url(), url(), …`, pointing to an image file.
More than one [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value) may be provided as fallbacks, in case some cursor image types are not supported.
A non-URL fallback (one or more of the keyword values) _must_ be at the end of the fallback list.

[`<x>`, `<y>` Optional](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor#x)

Optional x- and y-coordinates indicating the cursor hotspot; the precise position within the cursor that is being pointed to.

The numbers are in units of image pixels.
They are relative to the top left corner of the image, which corresponds to `0 0`, and are clamped within the boundaries of the cursor image.
If these values are not specified, they may be read from the file itself, and will otherwise default to the top-left corner of the image.

[`keyword`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor#keyword)

A keyword value _must_ be specified, indicating either the type of cursor to use, or the fallback cursor to use if all specified icons fail to load.

The available keywords are listed in the table below. Other than `none`, which means no cursor, there is an image showing how the cursors used to be rendered. You can hover your mouse over the table rows to see the effect of the different cursor keyword values on your browser today.

| Category | Keyword | Example | Description |
| --- | --- | --- | --- |
| General | `auto` |  | The UA will determine the cursor to display based on the current context. E.g., equivalent to `text` when hovering text. |
| `default` | ![wide arrow pointing up and to the left](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/default.gif) | The platform-dependent default cursor. Typically an arrow. |
| `none` |  | No cursor is rendered. |
| Links & status | `context-menu` | ![wide arrow pointing up and to the left slightly obscuring a menu icon](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/context-menu.png) | A context menu is available. |
| `help` | ![wide arrow pointing up and to the left next to a question mark](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/help.gif) | Help information is available. |
| `pointer` | ![right hand with an index finger pointing up](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/pointer.gif) | The cursor is a pointer that indicates a link. Typically an image of a pointing hand. |
| `progress` | ![wide arrow and hour glass](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/progress.gif) | The program is busy in the background, but the user can still interact<br> with the interface (in contrast to `wait`). |
| `wait` | ![hour glass](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/wait.gif) | The program is busy, and the user can't interact with the interface (in contrast to `progress`).<br> Sometimes an image of an hourglass or a watch. |
| Selection | `cell` | ![wide plus symbol](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/cell.gif) | The table cell or set of cells can be selected. |
| `crosshair` | ![plus symbol composed of two thin lines.](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/crosshair.gif) | Cross cursor, often used to indicate selection in a bitmap. |
| `text` | ![vertical i-beam](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/text.gif) | The text can be selected. Typically the shape of an I-beam. |
| `vertical-text` | ![horizontal i-beam](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/vertical-text.gif) | The vertical text can be selected. Typically the shape of a sideways I-beam. |
| Drag & drop | `alias` | ![wide arrow pointing up and to the left partially obscuring a smaller folder icon with a curved arrow pointing up and to the right](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/alias.gif) | An alias or shortcut is to be created. |
| `copy` | ![wide arrow pointing up and to the left partially obscuring a smaller folder icon with a plus sign](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/copy.gif) | Something is to be copied. |
| `move` | ![plus sign made of two thin lines. The four points are small arrows facing out](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/move.gif) | Something is to be moved. |
| `no-drop` | ![pointer icon and a not allowed icon](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/no-drop.gif) | An item may not be dropped at the current location.<br>[Firefox bug 275173](https://bugzil.la/275173):<br> On Windows and macOS, `no-drop` is the same as `not-allowed`. |
| `not-allowed` | ![Not allowed icon, which is a circle with a line through it](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/not-allowed.gif) | The requested action will not be carried out. |
| `grab` | ![fully opened hand icon](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/grab.gif) | Something can be grabbed (dragged to be moved). |
| `grabbing` | ![closed hand icon, of the back of the hand](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/grabbing.gif) | Something is being grabbed (dragged to be moved). |
| Resizing & scrolling | `all-scroll` | ![icon of a medium size dot with four triangles around it.](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/all-scroll.gif) | Something can be scrolled in any direction (panned).<br>[Firefox bug 275174](https://bugzil.la/275174):<br> On Windows, `all-scroll` is the same as `move`. |
| `col-resize` | ![col-resize.gif](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/col-resize.gif) | The item/column can be resized horizontally.<br> Often rendered as arrows pointing left and right with a vertical bar separating them. |
| `row-resize` | ![two narrow parallel horizontal lines with a small arrow pointing up and another pointing down](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/row-resize.gif) | The item/row can be resized vertically.<br> Often rendered as arrows pointing up and down with a horizontal bar separating them. |
| `n-resize` | ![thin long arrow pointing towards the top](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/n-resize.gif) | Some edge is to be moved. For example, the `se-resize` cursor is used when the movement starts from the _south-east_ corner of the box.<br> In some environments, an equivalent bidirectional resize cursor is shown.<br> For example, `n-resize` and `s-resize` are the same as `ns-resize`. |
| `e-resize` | ![thin long arrow pointing towards the right](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/e-resize.gif) |
| `s-resize` | ![thin long arrow pointing down](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/s-resize.gif) |
| `w-resize` | ![thin long arrow pointing towards the left](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/w-resize.gif) |
| `ne-resize` | ![thin long arrow pointing top-right](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/ne-resize.gif) |
| `nw-resize` | ![thin long arrow pointing top-left](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/nw-resize.gif) |
| `se-resize` | ![thin long arrow pointing bottom-right](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/se-resize.gif) |
| `sw-resize` | ![thin long arrow pointing bottom-left](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/sw-resize.gif) |
| `ew-resize` | ![thin long arrow pointing left and right](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/3-resize.gif) | Bidirectional resize cursor. |
| `ns-resize` | ![thin long arrow pointing up and down](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/6-resize.gif) |
| `nesw-resize` | ![thin long arrow pointing both to the top-right and bottom-left](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/1-resize.gif) |
| `nwse-resize` | ![thin long arrow pointing both to the top-left and bottom-right](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/4-resize.gif) |
| Zooming | `zoom-in` | ![magnifying glass with a plus sign](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/zoom-in.gif) | Something can be zoomed (magnified) in or out. |
| `zoom-out` | ![magnifying glass with a minus sign](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/zoom-out.gif) |

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `auto` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | yes |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified, but with [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value) values made absolute |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#formal_syntax)

```
cursor =
  <cursor-image> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <cursor-predefined>

<cursor-image> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<url>](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") <url-set>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<number>](https://developer.mozilla.org/en-US/docs/Web/CSS/number) [{2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<cursor-predefined> =
  auto            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  default         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  none            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  context-menu    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  help            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  pointer         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  progress        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  wait            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  cell            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  crosshair       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  text            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  vertical-text   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  alias           [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  copy            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  move            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  no-drop         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  not-allowed     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  grab            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  grabbing        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  e-resize        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  n-resize        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ne-resize       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  nw-resize       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  s-resize        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  se-resize       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  sw-resize       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  w-resize        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ew-resize       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ns-resize       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  nesw-resize     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  nwse-resize     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  col-resize      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  row-resize      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  all-scroll      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  zoom-in         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  zoom-out

```

## [Usage notes](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#usage_notes)

### [Icon size limits](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#icon_size_limits)

While the specification does not limit the `cursor` image size, [user agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) commonly restrict them to avoid potential misuse.
For example, on Firefox and Chromium cursor images are restricted to 128x128 pixels by default, but it is recommended to limit the cursor image size to 32x32 pixels. Cursor changes using images that are larger than the user-agent maximum supported size will generally just be ignored.

### [Supported image file formats](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#supported_image_file_formats)

User agents are required by the specification to support PNG files, SVG v1.1 files in secure static mode that contain a natural size, and any other non-animated image file formats that they support for images in other properties.
Desktop browsers also broadly support the `.cur` file format.

The specification further indicates that user agents _should_ also support SVG v1.1 files in secure animated mode that contain a natural size, along with any other animated images file formats they support for images in other properties.
User agents _may_ support both static and animated SVG images that do not contain a natural size.

### [iPadOS](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#ipados)

iPadOS supports pointer devices like trackpads and mouses. By default, the iPad cursor is displayed as a circle, and the only supported value that will change an appearance of the pointer is `text`.

### [Other notes](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#other_notes)

Cursor changes that intersect toolbar areas are commonly blocked to avoid spoofing.

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#examples)

### [Setting cursor types](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#setting_cursor_types)

cssCopy

```
.foo {
  cursor: crosshair;
}

.bar {
  cursor: zoom-in;
}

/* A fallback keyword value is required when using a URL */
.baz {
  cursor: url("hyper.cur"), auto;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#specifications)

| Specification |
| --- |
| [CSS Basic User Interface Module Level 4\<br>\# cursor](https://drafts.csswg.org/css-ui/#cursor) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor\#see_also)

- [`pointer-events`](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events)
- [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value) type
- SVG [`cursor`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/cursor) attribute

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 5, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/cursor/index.md?plain=1 "Folder: ⁨en-us/web/css/cursor⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcursor&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcursor%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcursor%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcursor%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9944f7b12ef1a6aecd54d4b2f0c188a82fdeaaf0%0A*+Document+last+modified%3A+2025-08-05T13%3A32%3A56.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")