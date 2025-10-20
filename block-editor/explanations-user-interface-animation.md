---
url: https://developer.wordpress.org/block-editor/explanations/user-interface/animation
scraped_at: 2025-10-20T03:19:49.050Z
---

[Skip to content](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Animation


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Explanations](https://developer.wordpress.org/block-editor/explanations/)[User Interface](https://developer.wordpress.org/block-editor/explanations/user-interface/)Animation

Search

# Animation

## In this article

Table of Contents

- [Principles](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#principles)
  - [Point of Origin](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#point-of-origin)
  - [Speed](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#speed)
  - [Simple](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#simple)
  - [Consistency](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#consistency)
- [Accessibility Considerations](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#accessibility-considerations)
- [Inventory of Reused Animations](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#inventory-of-reused-animations)

[↑ Back to top](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/#wp--skip-link--target)

Animation can help reinforce a sense of hierarchy and spatial orientation. This document goes into principles you should follow when you add animation.

## [Principles](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/\#principles)

### [Point of Origin](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/\#point-of-origin)

- Animation can help anchor an interface element. For example a menu can scale up from the button that opened it.
- Animation can help give a sense of place; for example a sidebar can animate in from the side, implying it was always hidden off-screen.
- Design your animations as if you’re working with real-world materials. Imagine your user interface elements are made of real materials — when not on screen, where are they? Use animation to help express that.

### [Speed](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/\#speed)

- Animations should never block a user interaction. They should be fast, almost always complete in less than 0.2 seconds.
- A user should not have to wait for an animation to finish before they can interact.
- Animations should be performant. Use `transform` CSS properties when you can, these render elements on the GPU, making them smooth.
- If an animation can’t be made fast & performant, leave it out.

### [Simple](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/\#simple)

- Don’t bounce if the material isn’t made of rubber.
- Don’t rotate, fold, or animate on a curved path. Keep it simple.

### [Consistency](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/\#consistency)

In creating consistent animations, we have to establish physical rules for how elements behave when animated. When all animations follow these rules, they feel consistent, related, and predictable. An animation should match user expectations, if it doesn’t, it’s probably not the right animation for the job.

Reuse animations if one already exists for your task.

## [Accessibility Considerations](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/\#accessibility-considerations)

- Animations should be subtle. Be cognizant of users with [vestibular disorders triggered by motion](https://www.ncbi.nlm.nih.gov/pubmed/29017000).
- Don’t animate elements that are currently reporting content to adaptive technology (e.g., an `aria-live` region that’s receiving updates). This can cause confusion wherein the technology tries to parse a region that’s actively changing.
- Avoid animations that aren’t directly triggered by user behaviors.
- Whenever possible, ensure that animations respect the OS-level “Reduce Motion” settings. This can be done by utilizing the [`prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) media query. Gutenberg includes a `@reduce-motion` mixin for this, to be used alongside rules that include a CSS `animate` property.

## [Inventory of Reused Animations](https://developer.wordpress.org/block-editor/explanations/user-interface/animation/\#inventory-of-reused-animations)

The generic `Animate` component is used to animate different parts of the interface. See [the component documentation](https://developer.wordpress.org/block-editor/reference-guide/components/animate/) for more details about the available animations.

First published

February 5, 2022

Last updated

October 17, 2025

Edit article

[Improve it on GitHub: Animation](https://github.com/WordPress/gutenberg/edit/trunk/docs/explanations/user-interface/animation.md)

[PreviousBlock DesignPrevious: Block Design](https://developer.wordpress.org/block-editor/explanations/user-interface/block-design/)

[NextResourcesNext: Resources](https://developer.wordpress.org/block-editor/explanations/user-interface/design-resources/)

Notifications