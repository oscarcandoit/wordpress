---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/url_function
scraped_at: 2025-10-20T03:00:53.226Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function#search)

# url()


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Furl_function&level=high)

The **`url()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) is used to include a file. The parameter is an absolute URL, a relative URL, a blob URL, or a data URL. The **`url()`** function can be passed as a parameter of another CSS function, like the [`attr()`](https://developer.mozilla.org/en-US/docs/Web/CSS/attr) function. Depending on the property for which it is a value, the resource sought can be an image, font, or a stylesheet. The `url()` functional notation is the value for the `<url>` data type.

**Note:**
There is a difference between a [URI](https://developer.mozilla.org/en-US/docs/Glossary/URI) and a [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL). A URI identifies a resource. A URL is a type of URI, and describes the _location_ of a resource. A URI can be either a URL or a name ( [URN](https://developer.mozilla.org/en-US/docs/Glossary/URN)) of a resource.

In CSS Level 1, the `url()` functional notation described only true URLs. In CSS Level 2, the definition of `url()` was extended to describe any URI, whether a URL or a URN. Confusingly, this meant that `url()` could be used to create a `<uri>` CSS data type. This change was not only awkward but, debatably, unnecessary, since URNs are almost never used in actual CSS. To alleviate the confusion, CSS Level 3 returned to the narrower, initial definition. Now, `url()` denotes only true `<url>` s.

Relative URLs, if used, are relative to the URL of the stylesheet (not to the URL of the web page).

The **`url()`** function can be included as a value for
[`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background), [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image), [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border), [`border-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image), [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source), [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content), [`cursor`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor), [`filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter), [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style), [`list-style-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image), [`mask`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask), [`mask-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image), [`offset-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path), [`clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path),
[src](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/src) as part of a [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face) block, and [@counter-style/ `symbol`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/symbols)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#syntax)

css

```
/* Basic usage */
url("https://example.com/images/myImg.jpg");
url('https://example.com/images/myImg.jpg');
url(https://example.com/images/myImg.jpg);
url("data:image/jpeg;base64,iRxVB0…");
url(myImg.jpg);
url(#IDofSVGpath);

/* associated properties */
background-image: url("star.gif");
list-style-image: url('../images/bullet.jpg');
content: url("my-icon.jpg");
cursor: url(my-cursor.cur);
border-image-source: url(/media/diamonds.png);
src: url('fantastic-font.woff');
offset-path: url(#path);
mask-image: url("masks.svg#mask1");

/* Properties with fallbacks */
cursor: url(pointer.cur), pointer;

/* Associated short-hand properties */
background: url('star.gif') bottom right repeat-x blue;
border-image: url("/media/diamonds.png") 30 fill / 30px / 30px space;

/* As a parameter in another CSS function */
background-image: cross-fade(20% url(first.png), url(second.png));
mask-image: image(url(mask.png), skyblue, linear-gradient(black, transparent));

/* as part of a non-shorthand multiple value */
content: url(star.svg) url(star.svg) url(star.svg) url(star.svg) url(star.svg);

/* at-rules */
@document url("https://www.example.com/") { /* … */ }
@import url("https://www.example.com/style.css");
@namespace url(http://www.w3.org/1999/xhtml);

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#values)

[`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function#string)

A string specifying a URL, which is a relative or absolute address, or pointer, to the web resource to be included, or a data URL. You can also use a hash URL to reference the ID of an [SVG shape](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorials/SVG_from_scratch/Basic_shapes) or an [SVG filter](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/filter).

The quotes are generally optional—they are required if the URL includes parentheses, whitespace, or quotes (unless these characters are escaped), or if the address includes control characters above 0x7e. Normal string syntax rules apply: double quotes cannot occur inside double quotes and single quotes cannot occur inside single quotes unless escaped.

[`<url-modifier>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function#url-modifier)

In the future, the `url()` function may support specifying a modifier, an identifier or a functional notation, which alters the meaning of the URL string. This is not supported and not fully defined in the specification.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#formal_syntax)

```
<url()> =
  url(  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string) <url-modifier> [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times") )   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <url-token>

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#examples)

### [As the background property value](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#as_the_background_property_value)

css

```
body {
  background: url("https://mdn.github.io/shared-assets/images/examples/leopard.jpg")
    #0000dd no-repeat fixed;
}

```

### [For setting an image as a list bullet](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#for_setting_an_image_as_a_list_bullet)

```
<ul>
  <li>one</li>
  <li>two</li>
  <li>there</li>
</ul>

```

```
ul {
  font-size: 3rem;
  margin: 0;
}

```

css

```
ul {
  list-style: outside
    url("https://mdn.github.io/shared-assets/images/examples/firefox-logo.svg");
}

```

### [Usage in the content property](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#usage_in_the_content_property)

#### HTML

html

```
<ul>
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
</ul>

```

#### CSS

css

```
li::after {
  content: " - "
    url("https://mdn.github.io/shared-assets/images/examples/star-white_16x16.png");
}

```

#### Result

### [Using a data URL](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#using_a_data_url)

#### CSS

css

```
body {
  background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='90' height='45'%3E%3Cpath d='M10 10h60' stroke='%2300F' stroke-width='5'/%3E%3Cpath d='M10 20h60' stroke='%230F0' stroke-width='5'/%3E%3Cpath d='M10 30h60' stroke='red' stroke-width='5'/%3E%3C/svg%3E");
}

```

### [Usage in filters](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#usage_in_filters)

When a URL is used as a path for a filter, the URL must be one of the following:

1. The path to an SVG file with the ID of the filter appended.
2. the ID of the filter, if the SVG already exists on the page.

css

```
.blur {
  filter: url("my-file.svg#svg-blur"); /* the URL of an SVG file used as a filter */
}

.inline-blur {
  filter: url("#svg-blur"); /* the ID of an SVG that is embedded in the HTML page */
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#specifications)

| Specification |
| --- |
| [CSS Values and Units Module Level 4\<br>\# urls](https://drafts.csswg.org/css-values/#urls) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function\#see_also)

- [`<gradient>`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)
- [`element()`](https://developer.mozilla.org/en-US/docs/Web/CSS/element)
- [`image()`](https://developer.mozilla.org/en-US/docs/Web/CSS/image/image)
- [`image-set()`](https://developer.mozilla.org/en-US/docs/Web/CSS/image/image-set)
- [`cross-fade()`](https://developer.mozilla.org/en-US/docs/Web/CSS/cross-fade)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/url_function/index.md?plain=1 "Folder: ⁨en-us/web/css/url_function⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Furl_function&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Furl_function%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Furl_function%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Furl_function%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")