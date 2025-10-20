---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/important
scraped_at: 2025-10-20T03:00:38.661Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/important#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/important#search)

# !important

A `!` delimiter followed by the `important` keyword marks the declaration as important. The `!important` flag alters the rules selecting declarations inside the [cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade). A declaration that is not _important_ is called _normal_.

To mark a declaration important, add the _important flag_ ( `!important`) after the value in the declaration. While white space is allowed between the delimiter and the keyword, the flag is generally written as `!important` without any white space.

css

```
selector {
  property: value; /* normal declaration */
  property: value !important; /* important declaration (preferred) */
  property: value ! important; /* important declaration (not preferred) */
}

```

The `!important` comes after the value of the property value pair declaration, preceded by zero or more spaces. The important flag must be the last token in the declaration. In other words, there can be white space and comments between the flag and the declaration's ending semicolon, but nothing else.

## [Impact on the cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#impact_on_the_cascade)

When it comes to important declarations, the [cascade origin and layer orders](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade) are reversed. Without the important flag, declarations in the author's style sheets override declarations in a user's style sheet, which override declarations in the user-agent's default style sheet.

When a declaration is important, the order of precedence is reversed. Declarations marked as important in the user-agent style sheets override all important declarations in the user style sheets. Similarly, all important declarations in the user style sheets override all important declarations in the author's style sheets. Finally, all important declarations take precedence over all animations.

**Note:**
All important declarations take precedence over all animations. `!important` is not valid within [@keyframes animation](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) declarations.

Reversing the precedence order for important declarations ensures users with special needs, such as personalized color schemes or large fonts, can override author styles when needed by marking some declarations in their user's style sheet as important. It also guarantees malicious extensions can't override important user-agent styles, which might break functionality or negatively impact security.

Does anything have precedence over important declarations? Yes, [transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transitions). CSS transitions are a way to control the speed at which the property changes from one value to another. While transitioning from one value to another, a property will not match a specific important declaration.

css

```
a {
  color: red !important;
  background-color: yellow;
  transition: all 2s linear;
}
a:hover {
  color: blue !important;
  background-color: orange !important;
}

```

In this example, the `color` and `background-color` properties will transition to the hovered state over two seconds. Even though default states are normal declarations and hover states are `!important` declarations, the transition does happen.

### [Cascade layers](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#cascade_layers)

Within each of the three origins for style sheets – author, user, and user-agent – normal declarations in unlayered styles override layered style declarations, with the last declared having precedence over the layers declared before it. Important declarations reverse the order of precedence: important declarations in the first layer take precedence over important declarations in the next layer, and so on. Also, all the important declarations have precedence over important declarations made outside any layer.

### [Inline styles](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#inline_styles)

Inline styles are styles defined using the [`style`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/style) attributes. They can also be normal or important. Inline _normal_ styles take precedence over all _normal_ declarations, no matter the origin. Inline _important_ styles take precedence over all other _important_ author styles, no matter the layer, but important styles from user's or user-agent's style sheets and transitions override them.

### [!important and specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#!important_and_specificity)

While `!important` is not part of determining specificity, it is related. Important declarations override all other declarations from the same [origin and cascade layer](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade).

css

```
#myElement#myElement#myElement .myClass.myClass p:hover {
  color: blue;
}

p {
  color: red !important;
}

```

This example displays a case of over-specifying a selector. No matter how high the selector [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity) matches a normal declaration, an important declaration from the same source and cascade layer will always have precedence. In this case, the paragraph will always be red.

When two important declarations from the same origin and layer apply to the same element, browsers select and use the declaration with the highest specificity.

css

```
#myElement p {
  color: green !important;
}

p {
  color: purple !important;
}

```

In this case, the selector specificity matters. Only if the selectors had the same specificity would source order matter.

## [Impact on shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#impact_on_shorthand_properties)

Declaring a shorthand property with `!important` sets all of sub-properties as important. The two following selector style blocks are equivalent:

css

```
p {
  background: blue !important;
}

p {
  background-image: none !important;
  background-position: 0 0 !important;
  background-size: auto auto !important;
  background-repeat: repeat !important;
  background-origin: padding-box !important;
  background-clip: border-box !important;
  background-attachment: scroll !important;
  background-color: blue !important;
}

```

This example shows one of the several reasons avoiding the important flag is generally recommended.

## [Impact on custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#impact_on_custom_properties)

When the `!important` flag is added to a custom property value declaration, it makes the value assignment important. The `!important` flag is then stripped from the custom property value. The `!important` flag is not passed as part of the custom property value to the [`var()`](https://developer.mozilla.org/en-US/docs/Web/CSS/var) function.

css

```
:root {
  --my-color: red !important;
  --my-color: blue;
}
p {
  color: var(--my-color);
}
blockquote {
  color: var(--my-color);
  color: purple;
}

```

```
<p>This is a paragraph</p>
<blockquote>This is a blockquote</blockquote>

```

In this example, the paragraph will be red, not blue, as the custom property value assignment is important. The blockquote will be purple, because the purple normal declaration comes after the normal red declaration.

## [Best practices](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#best_practices)

Avoid using `!important` to override specificity. When intentionally creating important declarations for UI requirements, comment in your CSS code to explain to maintainers why they should not override that feature.

Even when working to override high-specificity styles not under your control, such as styles in a 3rd party plugin declared with an [id selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors), you don't need to use `!important`. Consider instead importing the 3rd party stylesheet script into a [named or anonymous layer](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer) as your first cascade layer, instead of using `!important`. As long as the external styles do not include important declarations, your styles will take precedence over the widget styles, no matter the specificity.

If you need to override an external stylesheet containing important declarations, create a cascade layer containing the needed overrides, and declare that layer first.

### [Accessibility concerns](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#accessibility_concerns)

Important styles from a user stylesheet take precedence over the author style sheet's important declarations, meaning adding an `!important` flag to a site's styles will not prevent individual users with special requirements, such as large fonts, from being able to override your styles by adding important styles in their own user's style sheet.

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#browser_compatibility)

This feature is supported in all browsers.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/important\#see_also)

- [CSS Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity)
- [CSS Cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 5, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/important/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/important/index.md?plain=1 "Folder: ⁨en-us/web/css/important⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fimportant&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fimportant%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fimportant%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fimportant%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F635820782735cd00f71ce3929ff9377b091f8995%0A*+Document+last+modified%3A+2025-08-05T14%3A01%3A02.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")