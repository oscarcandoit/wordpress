---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size
scraped_at: 2025-10-20T03:15:39.078Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# <absolute-size>

The **`<absolute-size>`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_data_types) describes the absolute size keywords. This data type is used in the [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) shorthand and [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) properties.

The font size keywords are mapped to the deprecated HTML `size` attribute. See the [HTML size attribute](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#html_size_attribute) section below).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size\#syntax)

```
<absolute-size> = xx-small | x-small | small | medium | large | x-large | xx-large | xxx-large

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size\#values)

The `<absolute-size>` data type is defined using a keyword value chosen from the list below.

[`xx-small`](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#xx-small)

An absolute size 60% the size of `medium`. Mapped to the deprecated `size="1"`.

[`x-small`](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#x-small)

An absolute size 75% the size of `medium`.

[`small`](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#small)

An absolute size 89% the size of `medium`. Mapped to the deprecated `size="2"`.

[`medium`](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#medium)

A user's preferred font size. This value is used as the reference middle value. Mapped to `size="3"`.

[`large`](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#large)

An absolute size 20% larger than `medium`. Mapped to the deprecated `size="4"`.

[`x-large`](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#x-large)

An absolute size 50% larger than `medium`. Mapped to the deprecated `size="5"`.

[`xx-large`](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#xx-large)

An absolute size twice the size of `medium`. Mapped to the deprecated `size="6"`.

[`xxx-large`](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#xxx-large)

An absolute size three times the size of `medium`. Mapped to the deprecated `size="7"`.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size\#description)

Each `<absolute-size>` keyword value is sized relative to the `medium` size and the individual device's characteristics, such as device resolution. User agents maintain a table of font sizes for each font, with the `<absolute-size>` keywords being the index.

In CSS1 (1996), the scaling factor between adjacent keyword value indexes was 1.5, which was too large. In CSS2 (1998), the scaling factor between adjacent keyword value indexes was 1.2, which created issues for the small values. As a single fixed ratio between adjacent absolute-size keywords was found to be problematic, there is no longer a fixed ratio recommendation. The only recommendation to preserve readability is that the smallest font size should not be less than `9px`.

For each `<absolute-size>` keyword value, the following table lists the scaling factor, mapping to [`<h1>` to `<h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/Heading_Elements) headings, and mapping to the deprecated [HTML `size` attribute](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size#html_size_attribute).

| `<absolute-size>` | xx-small | x-small | small | medium | large | x-large | xx-large | xxx-large |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| scaling factor | 3/5 | 3/4 | 8/9 | 1 | 6/5 | 3/2 | 2/1 | 3/1 |
| HTML headings | h6 |  | h5 | h4 | h3 | h2 | h1 |  |
| HTML `size` attribute | 1 |  | 2 | 3 | 4 | 5 | 6 | 7 |

### [HTML size attribute](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size\#html_size_attribute)

The `size` attribute to set a font's size in HTML is deprecated. The attribute value was either an integer between `1` and `7` or a relative value. Relative values were an integer preceded by `+` or `-` to increase or decrease the font size, respectively. A value of `+1` meant increasing the `size` by one and `-2` meant decreasing the size by two, with the computed value clamped at a minimum of `1` and a maximum computed value of `7`.

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size\#examples)

### [Comparing the keyword values](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size\#comparing_the_keyword_values)

htmlCopyPlay

```
<ul>
  <li class="xx-small">font-size: xx-small;</li>
  <li class="x-small">font-size: x-small;</li>
  <li class="small">font-size: small;</li>
  <li class="medium">font-size: medium;</li>
  <li class="large">font-size: large;</li>
  <li class="x-large">font-size: x-large;</li>
  <li class="xx-large">font-size: xx-large;</li>
  <li class="xxx-large">font-size: xxx-large;</li>
</ul>

```

cssCopyPlay

```
li {
  margin-bottom: 0.3em;
}
.xx-small {
  font-size: xx-small;
}
.x-small {
  font-size: x-small;
}
.small {
  font-size: small;
}
.medium {
  font-size: medium;
}
.large {
  font-size: large;
}
.x-large {
  font-size: x-large;
}
.xx-large {
  font-size: xx-large;
}
.xxx-large {
  font-size: xxx-large;
}

```

#### Result

Play

- font-size: xx-small;
- font-size: x-small;
- font-size: small;
- font-size: medium;
- font-size: large;
- font-size: x-large;
- font-size: xx-large;
- font-size: xxx-large;

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size\#specifications)

| Specification |
| --- |
| [CSS Fonts Module Level 4\<br>\# valdef-font-size-absolute-size](https://drafts.csswg.org/css-fonts/#valdef-font-size-absolute-size) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size\#see_also)

- CSS [`<relative-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/relative-size) data type
- CSS [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) and [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) properties
- [CSS fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/absolute-size/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/absolute-size/index.md?plain=1 "Folder: ⁨en-us/web/css/absolute-size⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fabsolute-size&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fabsolute-size%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fabsolute-size%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fabsolute-size%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")