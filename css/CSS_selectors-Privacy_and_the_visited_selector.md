---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector
scraped_at: 2025-10-20T03:08:45.240Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector#search)

# Privacy and the :visited selector

Originally, the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited) selector was a privacy and security risk. With a little bit of JavaScript, websites could uncover a user's browsing history and figure out what sites the user had visited. This was done using methods like [`window.getComputedStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle) and other techniques. This process was quick, enabling websites to not only determine where the user had been on the web, but also to guess a lot of information about the user's identity.

To mitigate this privacy concern, browsers limit the amount of information that can be obtained from visited links.

## [Little white lies](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector\#little_white_lies)

To preserve users' privacy, browsers lie to web applications under certain circumstances:

- The `window.getComputedStyle` method and similar functions, such as [`element.querySelector`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector), always return values indicating that a user has never visited any of the links on a page.
- When using a sibling selector, such as `:visited + span`, the adjacent element ( `span` in this example) is styled as though the link were unvisited.
- In rare scenarios, if you're using nested link elements and the element being matched is different from the link whose presence in history is being tested, the element will be rendered as though the link were unvisited.

## [Limits to visited link styles](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector\#limits_to_visited_link_styles)

You can style visited links, but there are limits to which styles you can use. Only the following styles can be applied to visited links:

- [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
- [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
- [`border-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color) (and its sub-properties)
- [`column-rule-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color)
- [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color)
- [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color)
- [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color)
- Color parts of the [`fill`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/fill) and [`stroke`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stroke) attributes

In addition, even for the styles mentioned above, transparency differences between unvisited and visited links are not applied. This restriction prevents the use of the `alpha` parameter in various [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) functions or the [`transparent`](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color#transparent) keyword to distinguish between the two states.

Here is an example of how to use styles with the aforementioned restrictions:

cssCopy

```
:link {
  outline: 1px dotted blue;
  background-color: white;
  /* The default value of `background-color` is `transparent`. You need to
     specify a different value, otherwise changes on `:visited` won't apply. */
}

:visited {
  outline-color: orange; /* Visited links have an orange outline */
  background-color: green; /* Visited links have a green background */
  color: yellow; /* Visited links have yellow colored text */
}

```

## [Impact on web developers](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector\#impact_on_web_developers)

You may want to consider the following when developing sites:

- Changing [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image) values based on a link's visited state will not work since only colors can be used to style visited links.
- Colors that are otherwise transparent will not apply when styled via a `:visited` selector.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector\#see_also)

- [Preventing attacks on a user's history through CSS `:visited` selectors](https://dbaron.org/mozilla/visited-privacy) (2010)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_selectors/privacy_and_the_visited_selector/index.md?plain=1 "Folder: ⁨en-us/web/css/css_selectors/privacy_and_the_visited_selector⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors%2FPrivacy_and_the_visited_selector&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_selectors%2Fprivacy_and_the_visited_selector%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors%2FPrivacy_and_the_visited_selector%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_selectors%2Fprivacy_and_the_visited_selector%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")