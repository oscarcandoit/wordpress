---
url: https://developer.wordpress.org/block-editor/contributors/code/managing-packages
scraped_at: 2025-10-20T03:19:10.138Z
---

[Skip to content](https://developer.wordpress.org/block-editor/contributors/code/managing-packages/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Managing Packages


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Contributor Guide](https://developer.wordpress.org/block-editor/contributors/)[Code Contributions](https://developer.wordpress.org/block-editor/contributors/code/)Managing Packages

Search

# Managing Packages

[↑ Back to top](https://developer.wordpress.org/block-editor/contributors/code/managing-packages/#wp--skip-link--target)

This repository uses [npm workspaces](https://docs.npmjs.com/cli/v10/using-npm/workspaces) to manage WordPress packages and [lerna](https://lerna.js.org/) to publish them to [npm](https://www.npmjs.com/). This enforces certain steps in the workflow which are described in details in [packages](https://github.com/WordPress/gutenberg/blob/HEAD/packages/README.md) documentation.

Maintaining dozens of npm packages is difficult—it can be tough to keep track of changes. That’s why we use `CHANGELOG.md` files for each package to simplify the release process. As a contributor, you should add an entry to the aforementioned file each time you contribute adding production code as described in [Maintaining Changelogs](https://github.com/WordPress/gutenberg/blob/HEAD/packages/README.md#maintaining-changelogs) section.

Publishing WordPress packages to npm is automated by synchronizing it with the bi-weekly Gutenberg plugin RC1 release. You can learn more about this process and other ways to publish new versions of npm packages in the [Gutenberg Release Process document](https://developer.wordpress.org/block-editor/contributors/code/release/#packages-releases-to-npm-and-wordpress-core-updates).

First published

March 10, 2021

Last updated

October 17, 2025

Edit article

[Improve it on GitHub: Managing Packages](https://github.com/WordPress/gutenberg/edit/trunk/docs/contributors/code/managing-packages.md)

[PreviousScriptsPrevious: Scripts](https://developer.wordpress.org/block-editor/contributors/code/scripts/)

[NextGutenberg Release ProcessNext: Gutenberg Release Process](https://developer.wordpress.org/block-editor/contributors/code/release/)

Notifications