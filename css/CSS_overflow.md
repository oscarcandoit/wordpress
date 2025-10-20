---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow
scraped_at: 2025-10-20T03:17:55.039Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow#search)

# CSS overflow

The **CSS overflow** module properties enable you to handle scrollable overflow in visual media.

Overflow happens when the content in an element box extends past one or more of the box's edges. **Scrollable overflow** is the content that appears outside the element box for which you might want to add a scrolling mechanism. CSS overflow properties let you control what happens when content overflows an element box, including creating carousels without JavaScript.

Painting effects that overflow the content but do not participate in the CSS box model do not affect layout. This type of overflow is also known as [ink overflow](https://developer.mozilla.org/en-US/docs/Glossary/Ink_overflow). Examples of ink overflows include box shadows, border images, text decoration, overhanging glyphs, and outlines. Ink overflows do not extend the scrollable overflow region.

## [Overflow in action](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#overflow_in_action)

Try the following example to see the effects of various `overflow` property values on the content overflow and scrollbars in the adjacent fixed-size box.

The example includes options to change the values for the `overflow-clip-margin` and `width` properties, as well as to programmatically scroll the content if the overflow property creates a [scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container). Select `overflow: clip` and see the effect of different `overflow-clip-margin` values. Select `overflow: hidden` or `overflow: scroll` to check out the various `ScrollLeft` and `ScrollTop` slider settings.

```
<article>
  <fieldset>
    <legend>Select options:</legend>
    <label
      ><code>overflow</code>:
      <select id="overflowValue">
        <option>hidden</option>
        <option>clip</option>
        <option>scroll</option>
        <option>auto</option>
        <option selected>visible</option>
        <option>overlay</option>
      </select>
    </label>
    <label>
      <code>overflow-clip-margin</code>:
      <input type="number" id="ocm" value="1" min="0" max="10" size="2" />
      <code>em</code>
    </label>
    <label
      ><input type="checkbox" id="wide" /> <code>width</code>:
      <code>20em</code> or <code>40em</code></label
    >
    <fieldset>
      <legend>Scroll programmatically:</legend>
      <label
        >ScrollLeft:
        <input type="range" min="0" max="100" value="0" id="scrollL"
      /></label>
      <label
        >ScrollTop:
        <input type="range" min="0" max="100" value="0" id="scrollT"
      /></label>
    </fieldset>
  </fieldset>
  <pre class="visible">&nbsp;
    Oh, Rubber Duckie, you're the one
    You make bath time lots of fun
    Rubber Duckie, I'm awfully fond of you

    Rubber Duckie, joy of joys
    When I squeeze you, you make noise
    Rubber Duckie, you're my very best friend, it's true

    Oh, every day when I make my way to the tubby
    I find a little fella who's cute and yellow and chubby
    Rub-a-dub-dubby

    <a href="#">Rubber Duckie</a>, you're so fine
    And I'm lucky that you're mine
    Rubber Duckie, I'm awfully fond of you
      </pre>
</article>

```

```
article {
  display: flex;
  gap: 1em;
}

label {
  display: block;
  white-space: nowrap;
}

pre {
  border: 2px dashed crimson;
  height: 150px;
  width: 20em;
  margin-bottom: 3em;
  overflow-clip-margin: 1em;
  text-align: center;
}

.wide {
  width: 40em;
}

::before {
  font-weight: bold;
  color: white;
  background: crimson;
  display: inline-block;
  min-width: 50%;
  padding: 3px 5px;
  box-sizing: border-box;
}

.hidden {
  overflow: hidden;
}
.hidden::before {
  content: "hidden: ";
}

.clip {
  overflow: clip;
}
.clip::before {
  content: "clip: ";
}

.scroll {
  overflow: scroll;
}
.scroll::before {
  content: "scroll: ";
}

.auto {
  overflow: auto;
}
.auto::before {
  content: "auto: ";
}

.overlay {
  overflow: clip;
  overflow: overlay;
}
.overlay::before {
  content: "overlay (or clip if not supported): ";
}

.visible {
  overflow: visible;
}
.visible::before {
  content: "visible: ";
}

article:not(:has(pre.clip)) > fieldset > label:nth-of-type(2),
article:not(:has(pre.hidden, pre.scroll, pre.auto, pre.overlay))
  fieldset
  fieldset {
  opacity: 20%;
  pointer-events: none;
}

```

```
const pre = document.querySelector("pre");
const val = document.getElementById("overflowValue");
const check = document.getElementById("wide");
const ocm = document.getElementById("ocm");
const scrollL = document.getElementById("scrollL");
const scrollT = document.getElementById("scrollT");

val.addEventListener("change", () => {
  if (pre.classList.contains("wide")) {
    pre.className = `wide ${val.value}`;
  } else {
    pre.className = `${val.value}`;
  }
  scrollExample();
  clipMargin();
});

wide.addEventListener("change", () => {
  pre.classList.toggle("wide");
  scrollExample();
});

ocm.addEventListener("change", () => {
  clipMargin();
});

scrollL.addEventListener("change", () => {
  scrollExample();
});
scrollT.addEventListener("change", () => {
  scrollExample();
});

function scrollExample() {
  pre.scrollTo({
    top: scrollT.value,
    left: scrollL.value * 2,
    behavior: "smooth",
  });
}

function clipMargin() {
  pre.style.overflowClipMargin = `${ocm.value}em`;
}

```

A link is included in the content box above to demonstrate the effects of keyboard focus on overflow and scroll behaviors. Try tabbing to the link or programmatically scrolling the content: the content will scroll only if the enumerated `<overflow>` value creates a scroll container.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#properties)

- [`line-clamp`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-clamp)
- [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) shorthand
- [`overflow-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-block)
- [`overflow-clip-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin)
- [`overflow-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-inline)
- [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x)
- [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y)
- [`scroll-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior)
- [`scroll-marker-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-marker-group)
- [`scroll-target-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-target-group)
- [`scrollbar-gutter`](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-gutter)
- [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow)

The CSS overflow level 4 module also introduces the `block-ellipsis`, `continue`, `max-lines`, `overflow-clip-margin-block`, `overflow-clip-margin-block-end`, `overflow-clip-margin-block-start`, `overflow-clip-margin-bottom`, `overflow-clip-margin-inline`, `overflow-clip-margin-inline-end`, `overflow-clip-margin-inline-start`, `overflow-clip-margin-left`, `overflow-clip-margin-right`, and `overflow-clip-margin-top` properties. Currently, no browsers support these features.

### [Selectors and pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#selectors_and_pseudo-elements)

- [`::scroll-button()`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-button)
- [`::scroll-marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker)
- [`::scroll-marker-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker-group)
- [`:target-current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target-current)

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#data_types)

- [`<overflow>`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow_value) enumerated values

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#guides)

[Learn: Overflowing content](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Overflow)

Learn what overflow is and how to manage it.

[Creating CSS carousels](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow/CSS_carousels)

Create pure-CSS carousel UI features using scroll buttons, scroll markers, and generated columns.

[Creating a named scroll progress timeline animation](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-name#creating_a_named_scroll_progress_timeline_animation)

The CSS scroll timeline [`scroll-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-name) and [`scroll-timeline-axis`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-axis) properties, along with the [`scroll-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline) shorthand, create animations tied to the scroll offset of a scroll container.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#related_concepts)

- [`::column`](https://developer.mozilla.org/en-US/docs/Web/CSS/::column)
- [`scrollbar-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-width) CSS property
- [`scrollbar-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-color) CSS property
- [`scrollbar-gutter`](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-gutter) CSS property
- [`scroll-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior) CSS property
- [`scroll-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin) CSS shorthand property
- [`scroll-padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding) CSS shorthand property
- [`scroll-snap-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-align) CSS property
- [`scroll-snap-stop`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-stop) CSS property
- [`scroll-snap-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type) CSS property
- [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) CSS property
- [`::-webkit-scrollbar`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-scrollbar) pseudo-element
- [`scrollbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/scrollbar_role) ARIA role
- Element [`scroll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll "scroll()") method
- Element [`scrollBy()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollBy "scrollBy()") method
- Element [`scrollIntoView()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView "scrollIntoView()") method
- Element [`scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo "scrollTo()") method
- Element [`scrollTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop "scrollTop") property
- Element [`scrollLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft "scrollLeft") property
- Element [`scrollWidth`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollWidth "scrollWidth") property
- Element [`scrollHeight`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollHeight "scrollHeight") property
- Document [`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event "scroll") event
- [Scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container) glossary term
- [Ink overflow](https://developer.mozilla.org/en-US/docs/Glossary/Ink_overflow) glossary term

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#specifications)

| Specification |
| --- |
| [CSS Overflow Module Level 3](https://drafts.csswg.org/css-overflow/) |
| [CSS Overflow Module Level 4](https://drafts.csswg.org/css-overflow-4/) |
| [CSS Overflow Module Level 5](https://drafts.csswg.org/css-overflow-5/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow\#see_also)

- [CSS scrollbars styling](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scrollbars_styling) module
- [CSS scroll snap](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_snap) module
- [CSSOM view](https://developer.mozilla.org/en-US/docs/Web/CSS/CSSOM_view) module
- How to [debug scrollable overflow](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/debug_scrollable_overflow/index.html)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Sep 19, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_overflow/index.md?plain=1 "Folder: ⁨en-us/web/css/css_overflow⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_overflow&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_overflow%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_overflow%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_overflow%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fad57cae3faaec374c3e712d6994e7fc3cb9318db%0A*+Document+last+modified%3A+2025-09-19T06%3A07%3A17.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")