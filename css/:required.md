---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/:required
scraped_at: 2025-10-20T03:14:42.657Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/:required#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/:required#search)

# :required


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:required#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Arequired&level=high)

The **`:required`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) represents any [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/textarea) element that has the [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input#required) attribute set on it.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/:required\#try_it)

```
label {
  display: block;
  margin-top: 1em;
}

.req {
  color: red;
}

*:required {
  background-color: gold;
}

```

```
<form>
  <label for="name">Name: <span class="req">*</span></label>
  <input id="name" name="name" type="text" required />

  <label for="birth">Date of Birth:</label>
  <input id="birth" name="birth" type="date" />

  <label for="origin"
    >How did you find out about us? <span class="req">*</span></label
  >
  <select id="origin" name="origin" required>
    <option>Google</option>
    <option>Facebook</option>
    <option>Advertisement</option>
  </select>
  <p><span class="req">*</span> - Required field</p>
</form>

```

This pseudo-class is useful for highlighting fields that must have valid data before a form can be submitted.

**Note:**
The [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional) pseudo-class selects _optional_ form fields.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/:required\#syntax)

css

```
:required {
  /* ... */
}

```

## [Accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:required\#accessibility)

Mandatory [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input) s should have the [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input#required) attribute applied to them. This will ensure that people navigating with the aid of assistive technology such as a screen reader will be able to understand which inputs need valid content to ensure a successful submission.

If the form also contains [optional](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional) inputs, required inputs should be indicated visually using a treatment that does not rely solely on color to convey meaning. Typically, descriptive text and/or an icon are used.

- [MDN Understanding WCAG, Guideline 3.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Understandable#guideline_3.3_%e2%80%94_input_assistance_help_users_avoid_and_correct_mistakes)
- [Understanding Success Criterion 3.3.2 \| W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-cues.html)

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/:required\#examples)

### [The required field has a red border](https://developer.mozilla.org/en-US/docs/Web/CSS/:required\#the_required_field_has_a_red_border)

#### HTML

html

```
<form>
  <div class="field">
    <label for="url_input">Enter a URL:</label>
    <input type="url" id="url_input" />
  </div>

  <div class="field">
    <label for="email_input">Enter an email address:</label>
    <input type="email" id="email_input" required />
  </div>
</form>

```

#### CSS

css

```
label {
  display: block;
  margin: 1px;
  padding: 1px;
}

.field {
  margin: 1px;
  padding: 1px;
}

input:required {
  border-color: maroon;
  border-width: 3px;
}

input:required:invalid {
  border-color: #c00000;
}

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/:required\#specifications)

| Specification |
| --- |
| [HTML\<br>\# selector-required](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-required) |
| [Selectors Level 4\<br>\# required-pseudo](https://drafts.csswg.org/selectors/#required-pseudo) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:required\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/:required\#see_also)

- Other validation-related pseudo-classes: [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional), [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid), [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)
- [Form data validation](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms/Form_validation)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 5, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/:required/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/_colon_required/index.md?plain=1 "Folder: ⁨en-us/web/css/_colon_required⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Arequired&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F_colon_required%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Arequired%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F_colon_required%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F7f460077d6f16c939718e9482a8270166f6d9abd%0A*+Document+last+modified%3A+2025-08-05T13%3A26%3A56.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")