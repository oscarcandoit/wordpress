---
url: https://getbootstrap.com/docs/5.3/components/modal
scraped_at: 2025-10-20T02:27:32.512Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/components/modal/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/components/modal/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/components/modal.mdx "View and edit this file on GitHub")

# Modal

Use Bootstrap’s JavaScript modal plugin to add dialogs to your site for lightboxes, user notifications, or completely custom content.

On this page
**On this page**

* * *

## How it works [Link to this section: How it works](https://getbootstrap.com/docs/5.3/components/modal/\#how-it-works)

Before getting started with Bootstrap’s modal component, be sure to read the following as our menu options have recently changed.

- Modals are built with HTML, CSS, and JavaScript. They’re positioned over everything else in the document and remove scroll from the `<body>` so that modal content scrolls instead.
- Clicking on the modal “backdrop” will automatically close the modal.
- Bootstrap only supports one modal window at a time. Nested modals aren’t supported as we believe them to be poor user experiences.
- Modals use `position: fixed`, which can sometimes be a bit particular about its rendering. Whenever possible, place your modal HTML in a top-level position to avoid potential interference from other elements. You’ll likely run into issues when nesting a `.modal` within another fixed element.
- Once again, due to `position: fixed`, there are some caveats with using modals on mobile devices. [See our browser support docs](https://getbootstrap.com/docs/5.3/getting-started/browsers-devices#modals-and-dropdowns-on-mobile) for details.
- Due to how HTML5 defines its semantics, [the `autofocus` HTML attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-autofocus) has no effect in Bootstrap modals. To achieve the same effect, use some custom JavaScript:

```js
const myModal = document.getElementById('myModal')
const myInput = document.getElementById('myInput')

myModal.addEventListener('shown.bs.modal', () => {
  myInput.focus()
})

```

The animation effect of this component is dependent on the `prefers-reduced-motion` media query. See the [reduced motion section of our accessibility documentation](https://getbootstrap.com/docs/5.3/getting-started/accessibility/#reduced-motion).

Keep reading for demos and usage guidelines.

## Examples [Link to this section: Examples](https://getbootstrap.com/docs/5.3/components/modal/\#examples)

### Modal components [Link to this section: Modal components](https://getbootstrap.com/docs/5.3/components/modal/\#modal-components)

Below is a _static_ modal example (meaning its `position` and `display` have been overridden). Included are the modal header, modal body (required for `padding`), and modal footer (optional). We ask that you include modal headers with dismiss actions whenever possible, or provide another explicit dismiss action.

```html
<div class="modal" tabindex="-1">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">Modal title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <p>Modal body text goes here.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>

```

In the above static example, we use `<h5>`, to avoid issues with the heading hierarchy in the documentation page. Structurally, however, a modal dialog represents its own separate document/context, so the `.modal-title` should ideally be an `<h1>`. If necessary, you can use the [font size utilities](https://getbootstrap.com/docs/5.3/utilities/text#font-size) to control the heading’s appearance. All the following live examples use this approach.

### Live demo [Link to this section: Live demo](https://getbootstrap.com/docs/5.3/components/modal/\#live-demo)

Toggle a working modal demo by clicking the button below. It will slide down and fade in from the top of the page.

Launch demo modal

```html
<!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>

```

### Static backdrop [Link to this section: Static backdrop](https://getbootstrap.com/docs/5.3/components/modal/\#static-backdrop)

When backdrop is set to static, the modal will not close when clicking outside of it. Click the button below to try it.

Launch static backdrop modal

```html
<!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#staticBackdrop">
  Launch static backdrop modal
</button>

<!-- Modal -->
<div class="modal fade" id="staticBackdrop" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1" aria-labelledby="staticBackdropLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="staticBackdropLabel">Modal title</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Understood</button>
      </div>
    </div>
  </div>
</div>

```

### Scrolling long content [Link to this section: Scrolling long content](https://getbootstrap.com/docs/5.3/components/modal/\#scrolling-long-content)

When modals become too long for the user’s viewport or device, they scroll independent of the page itself. Try the demo below to see what we mean.

Launch demo modal

You can also create a scrollable modal that allows scrolling the modal body by adding `.modal-dialog-scrollable` to `.modal-dialog`.

Launch demo modal

```html
<!-- Scrollable modal -->
<div class="modal-dialog modal-dialog-scrollable">
  ...
</div>

```

### Vertically centered [Link to this section: Vertically centered](https://getbootstrap.com/docs/5.3/components/modal/\#vertically-centered)

Add `.modal-dialog-centered` to `.modal-dialog` to vertically center the modal.

Vertically centered modalVertically centered scrollable modal

```html
<!-- Vertically centered modal -->
<div class="modal-dialog modal-dialog-centered">
  ...
</div>

<!-- Vertically centered scrollable modal -->
<div class="modal-dialog modal-dialog-centered modal-dialog-scrollable">
  ...
</div>

```

### Tooltips and popovers [Link to this section: Tooltips and popovers](https://getbootstrap.com/docs/5.3/components/modal/\#tooltips-and-popovers)

[Tooltips](https://getbootstrap.com/docs/5.3/components/tooltips) and [popovers](https://getbootstrap.com/docs/5.3/components/popovers) can be placed within modals as needed. When modals are closed, any tooltips and popovers within are also automatically dismissed.

Launch demo modal

```html
<div class="modal-body">
  <h2 class="fs-5">Popover in a modal</h2>
  <p>This <button class="btn btn-secondary" data-bs-toggle="popover" title="Popover title" data-bs-content="Popover body content is set in this attribute.">button</button> triggers a popover on click.</p>
  <hr>
  <h2 class="fs-5">Tooltips in a modal</h2>
  <p><a href="#" data-bs-toggle="tooltip" title="Tooltip">This link</a> and <a href="#" data-bs-toggle="tooltip" title="Tooltip">that link</a> have tooltips on hover.</p>
</div>

```

### Using the grid [Link to this section: Using the grid](https://getbootstrap.com/docs/5.3/components/modal/\#using-the-grid)

Utilize the Bootstrap grid system within a modal by nesting `.container-fluid` within the `.modal-body`. Then, use the normal grid system classes as you would anywhere else.

Launch demo modal

```html
<div class="modal-body">
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-4">.col-md-4</div>
      <div class="col-md-4 ms-auto">.col-md-4 .ms-auto</div>
    </div>
    <div class="row">
      <div class="col-md-3 ms-auto">.col-md-3 .ms-auto</div>
      <div class="col-md-2 ms-auto">.col-md-2 .ms-auto</div>
    </div>
    <div class="row">
      <div class="col-md-6 ms-auto">.col-md-6 .ms-auto</div>
    </div>
    <div class="row">
      <div class="col-sm-9">
        Level 1: .col-sm-9
        <div class="row">
          <div class="col-8 col-sm-6">
            Level 2: .col-8 .col-sm-6
          </div>
          <div class="col-4 col-sm-6">
            Level 2: .col-4 .col-sm-6
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

```

### Varying modal content [Link to this section: Varying modal content](https://getbootstrap.com/docs/5.3/components/modal/\#varying-modal-content)

Have a bunch of buttons that all trigger the same modal with slightly different contents? Use `event.relatedTarget` and [HTML `data-bs-*` attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) to vary the contents of the modal depending on which button was clicked.

Below is a live demo followed by example HTML and JavaScript. For more information, [read the modal events docs](https://getbootstrap.com/docs/5.3/components/modal/#events) for details on `relatedTarget`.

Open modal for @mdoOpen modal for @fatOpen modal for @getbootstrap

html

```html
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal" data-bs-whatever="@mdo">Open modal for @mdo</button>
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal" data-bs-whatever="@fat">Open modal for @fat</button>
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal" data-bs-whatever="@getbootstrap">Open modal for @getbootstrap</button>

<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">New message</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <form>
          <div class="mb-3">
            <label for="recipient-name" class="col-form-label">Recipient:</label>
            <input type="text" class="form-control" id="recipient-name">
          </div>
          <div class="mb-3">
            <label for="message-text" class="col-form-label">Message:</label>
            <textarea class="form-control" id="message-text"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Send message</button>
      </div>
    </div>
  </div>
</div>
```

[site/src/assets/partials/snippets.js](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/assets/partials/snippets.js)

```js
const exampleModal = document.getElementById('exampleModal')
if (exampleModal) {
  exampleModal.addEventListener('show.bs.modal', event => {
    // Button that triggered the modal
    const button = event.relatedTarget
    // Extract info from data-bs-* attributes
    const recipient = button.getAttribute('data-bs-whatever')
    // If necessary, you could initiate an Ajax request here
    // and then do the updating in a callback.

    // Update the modal's content.
    const modalTitle = exampleModal.querySelector('.modal-title')
    const modalBodyInput = exampleModal.querySelector('.modal-body input')

    modalTitle.textContent = `New message to ${recipient}`
    modalBodyInput.value = recipient
  })
}

```

### Toggle between modals [Link to this section: Toggle between modals](https://getbootstrap.com/docs/5.3/components/modal/\#toggle-between-modals)

Toggle between multiple modals with some clever placement of the `data-bs-target` and `data-bs-toggle` attributes. For example, you could toggle a password reset modal from within an already open sign in modal. **Please note multiple modals cannot be open at the same time**—this method simply toggles between two separate modals.

Open first modal

html

```html
<div class="modal fade" id="exampleModalToggle" aria-hidden="true" aria-labelledby="exampleModalToggleLabel" tabindex="-1">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalToggleLabel">Modal 1</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        Show a second modal and hide this one with the button below.
      </div>
      <div class="modal-footer">
        <button class="btn btn-primary" data-bs-target="#exampleModalToggle2" data-bs-toggle="modal">Open second modal</button>
      </div>
    </div>
  </div>
</div>
<div class="modal fade" id="exampleModalToggle2" aria-hidden="true" aria-labelledby="exampleModalToggleLabel2" tabindex="-1">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalToggleLabel2">Modal 2</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        Hide this modal and show the first with the button below.
      </div>
      <div class="modal-footer">
        <button class="btn btn-primary" data-bs-target="#exampleModalToggle" data-bs-toggle="modal">Back to first</button>
      </div>
    </div>
  </div>
</div>
<button class="btn btn-primary" data-bs-target="#exampleModalToggle" data-bs-toggle="modal">Open first modal</button>
```

### Change animation [Link to this section: Change animation](https://getbootstrap.com/docs/5.3/components/modal/\#change-animation)

The `$modal-fade-transform` variable determines the transform state of `.modal-dialog` before the modal fade-in animation, the `$modal-show-transform` variable determines the transform of `.modal-dialog` at the end of the modal fade-in animation.

If you want for example a zoom-in animation, you can set `$modal-fade-transform: scale(.8)`.

### Remove animation [Link to this section: Remove animation](https://getbootstrap.com/docs/5.3/components/modal/\#remove-animation)

For modals that simply appear rather than fade in to view, remove the `.fade` class from your modal markup.

```html
<div class="modal" tabindex="-1" aria-labelledby="..." aria-hidden="true">
  ...
</div>

```

### Dynamic heights [Link to this section: Dynamic heights](https://getbootstrap.com/docs/5.3/components/modal/\#dynamic-heights)

If the height of a modal changes while it is open, you should call `myModal.handleUpdate()` to readjust the modal’s position in case a scrollbar appears.

### Accessibility [Link to this section: Accessibility](https://getbootstrap.com/docs/5.3/components/modal/\#accessibility)

Be sure to add `aria-labelledby="..."`, referencing the modal title, to `.modal`. Additionally, you may give a description of your modal dialog with `aria-describedby` on `.modal`. Note that you don’t need to add `role="dialog"` since we already add it via JavaScript.

### Embedding YouTube videos [Link to this section: Embedding YouTube videos](https://getbootstrap.com/docs/5.3/components/modal/\#embedding-youtube-videos)

Embedding YouTube videos in modals requires additional JavaScript not in Bootstrap to automatically stop playback and more. [See this helpful Stack Overflow post](https://stackoverflow.com/questions/18622508/bootstrap-3-and-youtube-in-modal) for more information.

## Optional sizes [Link to this section: Optional sizes](https://getbootstrap.com/docs/5.3/components/modal/\#optional-sizes)

Modals have three optional sizes, available via modifier classes to be placed on a `.modal-dialog`. These sizes kick in at certain breakpoints to avoid horizontal scrollbars on narrower viewports.

| Size | Class | Modal max-width |
| --- | --- | --- |
| Small | `.modal-sm` | `300px` |
| Default | None | `500px` |
| Large | `.modal-lg` | `800px` |
| Extra large | `.modal-xl` | `1140px` |

Our default modal without modifier class constitutes the “medium” size modal.

Extra large modalLarge modalSmall modal

```html
<div class="modal-dialog modal-xl">...</div>
<div class="modal-dialog modal-lg">...</div>
<div class="modal-dialog modal-sm">...</div>

```

## Fullscreen Modal [Link to this section: Fullscreen Modal](https://getbootstrap.com/docs/5.3/components/modal/\#fullscreen-modal)

Another override is the option to pop up a modal that covers the user viewport, available via modifier classes that are placed on a `.modal-dialog`.

| Class | Availability |
| --- | --- |
| `.modal-fullscreen` | Always |
| `.modal-fullscreen-sm-down` | `576px` |
| `.modal-fullscreen-md-down` | `768px` |
| `.modal-fullscreen-lg-down` | `992px` |
| `.modal-fullscreen-xl-down` | `1200px` |
| `.modal-fullscreen-xxl-down` | `1400px` |

Full screenFull screen below smFull screen below mdFull screen below lgFull screen below xlFull screen below xxl

```html
<!-- Full screen modal -->
<div class="modal-dialog modal-fullscreen-sm-down">
  ...
</div>

```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/components/modal/\#css)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.3/components/modal/\#variables)

Added in v5.2.0

As part of Bootstrap’s evolving CSS variables approach, modals now use local CSS variables on `.modal` and `.modal-backdrop` for enhanced real-time customization. Values for the CSS variables are set via Sass, so Sass customization is still supported, too.

[scss/\_modal.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_modal.scss)

```scss
--#{$prefix}modal-zindex: #{$zindex-modal};
--#{$prefix}modal-width: #{$modal-md};
--#{$prefix}modal-padding: #{$modal-inner-padding};
--#{$prefix}modal-margin: #{$modal-dialog-margin};
--#{$prefix}modal-color: #{$modal-content-color};
--#{$prefix}modal-bg: #{$modal-content-bg};
--#{$prefix}modal-border-color: #{$modal-content-border-color};
--#{$prefix}modal-border-width: #{$modal-content-border-width};
--#{$prefix}modal-border-radius: #{$modal-content-border-radius};
--#{$prefix}modal-box-shadow: #{$modal-content-box-shadow-xs};
--#{$prefix}modal-inner-border-radius: #{$modal-content-inner-border-radius};
--#{$prefix}modal-header-padding-x: #{$modal-header-padding-x};
--#{$prefix}modal-header-padding-y: #{$modal-header-padding-y};
--#{$prefix}modal-header-padding: #{$modal-header-padding}; // Todo in v6: Split this padding into x and y
--#{$prefix}modal-header-border-color: #{$modal-header-border-color};
--#{$prefix}modal-header-border-width: #{$modal-header-border-width};
--#{$prefix}modal-title-line-height: #{$modal-title-line-height};
--#{$prefix}modal-footer-gap: #{$modal-footer-margin-between};
--#{$prefix}modal-footer-bg: #{$modal-footer-bg};
--#{$prefix}modal-footer-border-color: #{$modal-footer-border-color};
--#{$prefix}modal-footer-border-width: #{$modal-footer-border-width};

```

[scss/\_modal.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_modal.scss)

```scss
--#{$prefix}backdrop-zindex: #{$zindex-modal-backdrop};
--#{$prefix}backdrop-bg: #{$modal-backdrop-bg};
--#{$prefix}backdrop-opacity: #{$modal-backdrop-opacity};

```

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/components/modal/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$modal-inner-padding:               $spacer;

$modal-footer-margin-between:       .5rem;

$modal-dialog-margin:               .5rem;
$modal-dialog-margin-y-sm-up:       1.75rem;

$modal-title-line-height:           $line-height-base;

$modal-content-color:               var(--#{$prefix}body-color);
$modal-content-bg:                  var(--#{$prefix}body-bg);
$modal-content-border-color:        var(--#{$prefix}border-color-translucent);
$modal-content-border-width:        var(--#{$prefix}border-width);
$modal-content-border-radius:       var(--#{$prefix}border-radius-lg);
$modal-content-inner-border-radius: subtract($modal-content-border-radius, $modal-content-border-width);
$modal-content-box-shadow-xs:       var(--#{$prefix}box-shadow-sm);
$modal-content-box-shadow-sm-up:    var(--#{$prefix}box-shadow);

$modal-backdrop-bg:                 $black;
$modal-backdrop-opacity:            .5;

$modal-header-border-color:         var(--#{$prefix}border-color);
$modal-header-border-width:         $modal-content-border-width;
$modal-header-padding-y:            $modal-inner-padding;
$modal-header-padding-x:            $modal-inner-padding;
$modal-header-padding:              $modal-header-padding-y $modal-header-padding-x; // Keep this for backwards compatibility

$modal-footer-bg:                   null;
$modal-footer-border-color:         $modal-header-border-color;
$modal-footer-border-width:         $modal-header-border-width;

$modal-sm:                          300px;
$modal-md:                          500px;
$modal-lg:                          800px;
$modal-xl:                          1140px;

$modal-fade-transform:              translate(0, -50px);
$modal-show-transform:              none;
$modal-transition:                  transform .3s ease-out;
$modal-scale-transform:             scale(1.02);

```

### Sass loops [Link to this section: Sass loops](https://getbootstrap.com/docs/5.3/components/modal/\#sass-loops)

[Responsive fullscreen modals](https://getbootstrap.com/docs/5.3/components/modal/#fullscreen-modal) are generated via the `$breakpoints` map and a loop in `scss/_modal.scss`.

[scss/\_modal.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_modal.scss)

```scss
@each $breakpoint in map-keys($grid-breakpoints) {
  $infix: breakpoint-infix($breakpoint, $grid-breakpoints);
  $postfix: if($infix != "", $infix + "-down", "");

  @include media-breakpoint-down($breakpoint) {
    .modal-fullscreen#{$postfix} {
      width: 100vw;
      max-width: none;
      height: 100%;
      margin: 0;

      .modal-content {
        height: 100%;
        border: 0;
        @include border-radius(0);
      }

      .modal-header,
      .modal-footer {
        @include border-radius(0);
      }

      .modal-body {
        overflow-y: auto;
      }
    }
  }
}

```

## Usage [Link to this section: Usage](https://getbootstrap.com/docs/5.3/components/modal/\#usage)

The modal plugin toggles your hidden content on demand, via data attributes or JavaScript. It also overrides default scrolling behavior and generates a `.modal-backdrop` to provide a click area for dismissing shown modals when clicking outside the modal.

### Via data attributes [Link to this section: Via data attributes](https://getbootstrap.com/docs/5.3/components/modal/\#via-data-attributes)

#### Toggle [Link to this section: Toggle](https://getbootstrap.com/docs/5.3/components/modal/\#toggle)

Activate a modal without writing JavaScript. Set `data-bs-toggle="modal"` on a controller element, like a button, along with a `data-bs-target="#foo"` or `href="#foo"` to target a specific modal to toggle.

```html
<button type="button" data-bs-toggle="modal" data-bs-target="#myModal">Launch modal</button>

```

#### Dismiss [Link to this section: Dismiss](https://getbootstrap.com/docs/5.3/components/modal/\#dismiss)

Dismissal can be achieved with the `data-bs-dismiss` attribute on a button **within the modal** as demonstrated below:

```html
<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
```

or on a button **outside the modal** using the additional `data-bs-target` as demonstrated below:

```html
<button type="button" class="btn-close" data-bs-dismiss="modal" data-bs-target="#my-modal" aria-label="Close"></button>
```

While both ways to dismiss a modal are supported, keep in mind that dismissing from outside a modal does not match the [ARIA Authoring Practices Guide dialog (modal) pattern](https://www.w3.org/WAI/ARIA/apg/patterns/dialogmodal/). Do this at your own risk.

### Via JavaScript [Link to this section: Via JavaScript](https://getbootstrap.com/docs/5.3/components/modal/\#via-javascript)

Create a modal with a single line of JavaScript:

```js
const myModal = new bootstrap.Modal(document.getElementById('myModal'), options)
// or
const myModalAlternative = new bootstrap.Modal('#myModal', options)

```

### Options [Link to this section: Options](https://getbootstrap.com/docs/5.3/components/modal/\#options)

As options can be passed via data attributes or JavaScript, you can append an option name to `data-bs-`, as in `data-bs-animation="{value}"`. Make sure to change the case type of the option name from “ _camelCase_” to “ _kebab-case_” when passing the options via data attributes. For example, use `data-bs-custom-class="beautifier"` instead of `data-bs-customClass="beautifier"`.

As of Bootstrap 5.2.0, all components support an **experimental** reserved data attribute `data-bs-config` that can house simple component configuration as a JSON string. When an element has `data-bs-config='{"delay":0, "title":123}'` and `data-bs-title="456"` attributes, the final `title` value will be `456` and the separate data attributes will override values given on `data-bs-config`. In addition, existing data attributes are able to house JSON values like `data-bs-delay='{"show":0,"hide":150}'`.

The final configuration object is the merged result of `data-bs-config`, `data-bs-`, and `js object` where the latest given key-value overrides the others.

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| `backdrop` | boolean, `’static'` | `true` | Includes a modal-backdrop element. Alternatively, specify `static` for a backdrop which doesn’t close the modal when clicked. |
| `focus` | boolean | `true` | Puts the focus on the modal when initialized. |
| `keyboard` | boolean | `true` | Closes the modal when escape key is pressed. |

### Methods [Link to this section: Methods](https://getbootstrap.com/docs/5.3/components/modal/\#methods)

**All API methods are asynchronous and start a transition.** They return to the caller as soon as the transition is started, but before it ends. In addition, a method call on a transitioning component will be ignored. [Learn more in our JavaScript docs.](https://getbootstrap.com/docs/5.3/getting-started/javascript/#asynchronous-functions-and-transitions)

#### Passing options [Link to this section: Passing options](https://getbootstrap.com/docs/5.3/components/modal/\#passing-options)

Activates your content as a modal. Accepts an optional options `object`.

```js
const myModal = new bootstrap.Modal('#myModal', {
  keyboard: false
})

```

| Method | Description |
| --- | --- |
| `dispose` | Destroys an element’s modal. (Removes stored data on the DOM element) |
| `getInstance` | _Static_ method which allows you to get the modal instance associated with a DOM element. |
| `getOrCreateInstance` | _Static_ method which allows you to get the modal instance associated with a DOM element, or create a new one in case it wasn’t initialized. |
| `handleUpdate` | Manually readjust the modal’s position if the height of a modal changes while it is open (i.e. in case a scrollbar appears). |
| `hide` | Manually hides a modal. **Returns to the caller before the modal has actually been hidden** (i.e. before the `hidden.bs.modal` event occurs). |
| `show` | Manually opens a modal. **Returns to the caller before the modal has actually been shown** (i.e. before the `shown.bs.modal` event occurs). Also, you can pass a DOM element as an argument that can be received in the modal events (as the `relatedTarget` property). (i.e. `const modalToggle = document.getElementById('toggleMyModal'); myModal.show(modalToggle)`. |
| `toggle` | Manually toggles a modal. **Returns to the caller before the modal has actually been shown or hidden** (i.e. before the `shown.bs.modal` or `hidden.bs.modal` event occurs). |

### Events [Link to this section: Events](https://getbootstrap.com/docs/5.3/components/modal/\#events)

Bootstrap’s modal class exposes a few events for hooking into modal functionality. All modal events are fired at the modal itself (i.e. at the `<div class="modal">`).

| Event | Description |
| --- | --- |
| `hide.bs.modal` | This event is fired immediately when the `hide` instance method has been called. Can be prevented by calling `event.preventDefault()`. See [JavaScript events documentation](https://getbootstrap.com/docs/5.3/getting-started/javascript#events) for more details on event prevention. |
| `hidden.bs.modal` | This event is fired when the modal has finished being hidden from the user (will wait for CSS transitions to complete). |
| `hidePrevented.bs.modal` | This event is fired when the modal is shown, its backdrop is `static` and a click outside of the modal is performed. The event is also fired when the escape key is pressed and the `keyboard` option is set to `false`. |
| `show.bs.modal` | This event fires immediately when the `show` instance method is called. If caused by a click, the clicked element is available as the `relatedTarget` property of the event. |
| `shown.bs.modal` | This event is fired when the modal has been made visible to the user (will wait for CSS transitions to complete). If caused by a click, the clicked element is available as the `relatedTarget` property of the event. |

```js
const myModalEl = document.getElementById('myModal')
myModalEl.addEventListener('hidden.bs.modal', event => {
  // do something...
})

```