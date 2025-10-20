---
url: https://developer.wordpress.org/block-editor/contributors/code/react-native
scraped_at: 2025-10-20T03:20:02.131Z
---

[Skip to content](https://developer.wordpress.org/block-editor/contributors/code/react-native/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

React Native mobile editor


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Contributor Guide](https://developer.wordpress.org/block-editor/contributors/)[Code Contributions](https://developer.wordpress.org/block-editor/contributors/code/)React Native mobile editor

Search

# React Native mobile editor

## In this article

Table of Contents

- [Mind the mobile](https://developer.wordpress.org/block-editor/contributors/code/react-native/#mind-the-mobile)
- [Native mobile specific files](https://developer.wordpress.org/block-editor/contributors/code/react-native/#native-mobile-specific-files)
- [Running Gutenberg Mobile on Android and iOS](https://developer.wordpress.org/block-editor/contributors/code/react-native/#running-gutenberg-mobile-on-android-and-ios)
- [Native mobile E2E tests in Continuous Integration](https://developer.wordpress.org/block-editor/contributors/code/react-native/#native-mobile-e2e-tests-in-continuous-integration)
- [Debugging the native mobile unit tests](https://developer.wordpress.org/block-editor/contributors/code/react-native/#debugging-the-native-mobile-unit-tests)
- [Internationalization (i18n)](https://developer.wordpress.org/block-editor/contributors/code/react-native/#internationalization-i18n)

[↑ Back to top](https://developer.wordpress.org/block-editor/contributors/code/react-native/#wp--skip-link--target)

The Gutenberg repository includes the source for the [React Native](https://reactnative.dev/) based editor for mobile.

## [Mind the mobile](https://developer.wordpress.org/block-editor/contributors/code/react-native/\#mind-the-mobile)

Contributors need to ensure that they update any affected native mobile files during code refactorings because we cannot yet rely on automated tooling to do this for us. For example, renaming a function or a prop should also be performed in the native modules too, otherwise, the mobile client will break. We have added some mobile specific CI tests as safeguards in place in PRs, but we’re still far from done. Please bear with us and thank you in advance. ❤️🙇‍

## [Native mobile specific files](https://developer.wordpress.org/block-editor/contributors/code/react-native/\#native-mobile-specific-files)

The majority of the code shared with native mobile is in the very same JavaScript module and SASS style files. In the cases where the code paths need to diverge, a `.native.js` or `.native.scss` variant of the file is created. In some cases, platform specific files can be also found for Android ( `.android.js`) or iOS ( `.ios.js`).

## [Running Gutenberg Mobile on Android and iOS](https://developer.wordpress.org/block-editor/contributors/code/react-native/\#running-gutenberg-mobile-on-android-and-ios)

For instructions on how to run the **Gutenberg Mobile Demo App** on Android or iOS, see [Getting Started for the React Native based Mobile Gutenberg](https://developer.wordpress.org/block-editor/contributors/code/react-native/getting-started-react-native/)

Also, the mobile client is packaged and released via the [official WordPress apps](https://wordpress.org/mobile/). Even though the build pipeline is slightly different then the mobile demo apps and lives in its own repo for now ( [here’s the native mobile repo](https://github.com/wordpress-mobile/gutenberg-mobile)), the source code itself is taken directly from this repo and the “web” side codepaths.

## [Native mobile E2E tests in Continuous Integration](https://developer.wordpress.org/block-editor/contributors/code/react-native/\#native-mobile-e2e-tests-in-continuous-integration)

If you encounter a failed Android/iOS test on your pull request, we recommend the following steps:

1. Re-running the failed GitHub Action job ( [guide for how to re-run](https://docs.github.com/en/actions/configuring-and-managing-workflows/managing-a-workflow-run#viewing-your-workflow-history)) – This should fix failed tests the majority of the time.
2. You can check if the test is failing locally by following the steps to run the E2E test on your machine from the [E2E testing documentation](https://developer.wordpress.org/block-editor/reference-guide/packages/packages-react-native-editor/__device-tests__/).
3. In addition to reading the logs from the E2E test, you can download a video recording from the Artifacts section of the GitHub job that may have additional useful information.
4. Check if any changes in your PR would require corresponding changes to `.native.js` versions of files.
5. Lastly, if you’re stuck on a failing mobile test, feel free to reach out to contributors on Slack in the #mobile or #core-editor chats in the WordPress Core Slack, [free to join](https://make.wordpress.org/chat/).

## [Debugging the native mobile unit tests](https://developer.wordpress.org/block-editor/contributors/code/react-native/\#debugging-the-native-mobile-unit-tests)

Follow the instructions in [Native mobile testing](https://developer.wordpress.org/block-editor/contributors/code/react-native/integration-test-guide/) to locally debug the native mobile unit tests when needed.

## [Internationalization (i18n)](https://developer.wordpress.org/block-editor/contributors/code/react-native/\#internationalization-i18n)

Further information about this topic can be found in the [React Native Internationalization Guide](https://developer.wordpress.org/block-editor/contributors/code/react-native/internationalization-guide/).

First published

December 7, 2021

Last updated

October 17, 2025

Edit article

[Improve it on GitHub: React Native mobile editor](https://github.com/WordPress/gutenberg/edit/trunk/docs/contributors/code/react-native/README.md)

[PreviousCherry-picking automationPrevious: Cherry-picking automation](https://developer.wordpress.org/block-editor/contributors/code/release/auto-cherry-picking/)

[NextGetting Started for the React Native based Mobile GutenbergNext: Getting Started for the React Native based Mobile Gutenberg](https://developer.wordpress.org/block-editor/contributors/code/react-native/getting-started-react-native/)

Notifications