---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card
scraped_at: 2025-10-20T02:59:26.551Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2FLayout_cookbook%2FCard "Take survey (Opens in a new tab)")

# Card

This pattern is a list of "card" components with optional footers. A card contains a title, an image, a description or other content, and an attribution or footer. Cards are generally displayed within a group or collection.

![Three card components in a row](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card/cards.png)

## [Requirements](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card\#requirements)

Create a group of cards, with each card component containing a heading, image, content, and, optionally, a footer.

Each card in the group of cards should be the same height. The optional card footer should stick to the bottom of the card.

The cards in the group should line up in two dimensions — both vertically and horizontally.

## [Recipe](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card\#recipe)

Click "Play" in the code blocks below to edit the example in the MDN Playground:

htmlCopyPlay

```
<div class="cards">
  <article class="card">
    <header>
      <h2>A short heading</h2>
    </header>

    <img
      src="https://mdn.github.io/shared-assets/images/examples/balloons.jpg"
      alt="Hot air balloons" />
    <div class="content">
      <p>
        The idea of reaching the North Pole by means of balloons appears to have
        been entertained many years ago.
      </p>
    </div>
  </article>

  <article class="card">
    <header>
      <h2>A short heading</h2>
    </header>

    <img
      src="https://mdn.github.io/shared-assets/images/examples/balloons2.jpg"
      alt="Hot air balloons" />
    <div class="content">
      <p>Short content.</p>
    </div>
    <footer>I have a footer!</footer>
  </article>

  <article class="card">
    <header>
      <h2>A longer heading in this card</h2>
    </header>

    <img
      src="https://mdn.github.io/shared-assets/images/examples/balloons.jpg"
      alt="Hot air balloons" />
    <div class="content">
      <p>
        In a curious work, published in Paris in 1863 by Delaville Dedreux,
        there is a suggestion for reaching the North Pole by an aerostat.
      </p>
    </div>
    <footer>I have a footer!</footer>
  </article>
  <article class="card">
    <header>
      <h2>A short heading</h2>
    </header>

    <img
      src="https://mdn.github.io/shared-assets/images/examples/balloons2.jpg"
      alt="Hot air balloons" />
    <div class="content">
      <p>
        The idea of reaching the North Pole by means of balloons appears to have
        been entertained many years ago.
      </p>
    </div>
  </article>
</div>

```

cssCopyPlay

```
body {
  font: 1.2em sans-serif;
}

img {
  max-width: 100%;
}

.cards {
  max-width: 700px;
  margin: 1em auto;

  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
  grid-gap: 20px;
}

.card {
  border: 1px solid #999999;
  border-radius: 3px;

  display: grid;
  grid-template-rows: max-content 200px 1fr;
}

.card img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

.card h2 {
  margin: 0;
  padding: 0.5rem;
}

.card .content {
  padding: 0.5rem;
}

.card footer {
  background-color: #333333;
  color: white;
  padding: 0.5rem;
}

```

Play

![Hot air balloons](https://mdn.github.io/shared-assets/images/examples/balloons.jpg)

The idea of reaching the North Pole by means of balloons appears to have
been entertained many years ago.


![Hot air balloons](https://mdn.github.io/shared-assets/images/examples/balloons2.jpg)

Short content.

![Hot air balloons](https://mdn.github.io/shared-assets/images/examples/balloons.jpg)

In a curious work, published in Paris in 1863 by Delaville Dedreux,
there is a suggestion for reaching the North Pole by an aerostat.


![Hot air balloons](https://mdn.github.io/shared-assets/images/examples/balloons2.jpg)

The idea of reaching the North Pole by means of balloons appears to have
been entertained many years ago.


## [Choices made](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card\#choices_made)

Each card is laid out using [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) despite the layout being one-dimensional. This enables the use of content sizing for the grid tracks. To set up a single-column grid we can use the following:

cssCopy

```
.card {
  display: grid;
  grid-template-rows: max-content 200px 1fr;
}

```

[`display: grid`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) converts the element into a grid container. The three values of the [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows) property divide the grid into a minimum of three rows, defining the height of the first three children of the card, in order.

Each `card` contains a [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/header), [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img), and [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/div), in that order, with some also containing a [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/footer).

The heading row, or track, is set to [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-content), which prevents it from stretching. The image track is set to 200 pixels tall. The third track, where the content lives, is set to `1fr`. This means it will fill any additional space.

Any children beyond the three with explicitly defined sizes create rows in the implicit grid, which fits the content added to it. These are auto-sized by default. If a card contains a footer, it is auto-sized. The footer, when present, sticks to the bottom of the grid. The footer is auto-sized to fit its content; the content `<div>` then stretches take up any additional space.

The following ruleset creates the grid of cards:

cssCopy

```
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
  gap: 20px;
}

```

The [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns) property defines the widths of the grid columns. In this case, we set the grid to auto-fill, with repeated columns that are minimally `230px` but allowed to grow to fill the available space. The [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap) property sets a gap of `20px` between adjacent rows and adjacent columns.

**Note:**
The various elements in separate cards do not align with each other, as each card is an independent grid. Lining up the components in each card with the same components in adjacent cards can be done with [subgrid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Subgrid).

## [Alternative methods](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card\#alternative_methods)

[Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) can also be used to lay out each card. With flexbox, the dimensions of each card's rows are set with the [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) property on each row, rather than on the card container.

With flexbox, the dimensions of the flex items are defined on the children rather than the parent. Whether you choose to use grid or flexbox depends on your preference, whether you prefer controlling the tracks from the container or prefer adding rules to the items.

We chose grid for the cards as, generally, you want cards to be lined up both vertically and horizontally. Additionally, lining up the components within each card to the components of adjacent cards can be done with subgrid. Flex has no hack-free equivalent to subgrid.

## [Accessibility concerns](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card\#accessibility_concerns)

Depending on the content of your card, there may be things you could or should do to enhance accessibility. See [Inclusive components: Card](https://inclusive-components.design/cards/) by Heydon Pickering, for a very detailed explanation of these issues.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card\#see_also)

- [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
- [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows)
- [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
- [Inclusive components: Card](https://inclusive-components.design/cards/)
- [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Card/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/layout_cookbook/card/index.md?plain=1 "Folder: ⁨en-us/web/css/layout_cookbook/card⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FLayout_cookbook%2FCard&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Flayout_cookbook%2Fcard%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FLayout_cookbook%2FCard%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Flayout_cookbook%2Fcard%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F06639598f7805417a0331fe403304af9c7ecc2de%0A*+Document+last+modified%3A+2025-08-13T02%3A06%3A22.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")