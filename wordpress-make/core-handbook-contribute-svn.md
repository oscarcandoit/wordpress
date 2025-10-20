---
url: https://make.wordpress.org/core/handbook/contribute/svn/
scraped_at: 2025-10-20T02:59:16.091Z
---

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcore%2Fhandbook%2Fcontribute%2Fsvn%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[Skip to content](https://make.wordpress.org/core/handbook/contribute/svn/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Make WordPress Core](https://make.wordpress.org/core)

The Code Repository (SVN)

[Home](https://make.wordpress.org/core)[Handbook](https://make.wordpress.org/core/handbook/)[Contribute with Code](https://make.wordpress.org/core/handbook/contribute/)The Code Repository (SVN)

Search

# The Code Repository (SVN)

## In this article

Table of Contents

- [What is SVN?](https://make.wordpress.org/core/handbook/contribute/svn/#what-is-svn)
- [Finding an SVN Client](https://make.wordpress.org/core/handbook/contribute/svn/#finding-an-svn-client)
- [Learn More](https://make.wordpress.org/core/handbook/contribute/svn/#learn-more)

[↑ Back to top](https://make.wordpress.org/core/handbook/contribute/svn/#wp--skip-link--target)

WordPress supports patches being created from both [GIT](https://make.wordpress.org/core/handbook/contribute/git/) and SVN. This documentation focuses on the SVN option.

## [What is SVN?](https://make.wordpress.org/core/handbook/contribute/svn/\#what-is-svn)

WordPress uses [Subversion (SVN)](https://make.wordpress.org/core/glossary/#svn), a very popular version control system managed by the Apache project, to manage changes to its codebase. A change to the WordPress codebase increments the **revision** number. Individual changes are called [commits or changesets](https://make.wordpress.org/core/glossary/#commit-noun). These are denoted as either [r12345](https://core.trac.wordpress.org/changeset/12345) or \[ [12345](https://core.trac.wordpress.org/changeset/12345)\]. Details of the SVN and Git repositories are located [here](https://make.wordpress.org/core/handbook/contribute/codebase/).

The WordPress repository of code is organized into three main directories: [tags](https://make.wordpress.org/core/glossary/#tag), [branches](https://make.wordpress.org/core/glossary/#branch), and [trunk](https://make.wordpress.org/core/glossary/#trunk).

- The **trunk** directory contains the latest development code in preparation for the next major release cycle. The latest revision may be unstable or broken at times. The latest development code may be referred to as _trunk_.
- The **tags** directory contains individual snapshots of each official release, such as the 3.4.0 or 3.5.1 tags. Once created, these are unmodified, and these are used to build the download packages.
- The **branches** directory contains directories that consist of the latest code for each major release, such as the 3.4 and 3.5 branches. Minor release development occurs within the branch. For example, a critical bug that affects the latest release may be fixed in both trunk and the most recent branch, in preparation for a **point release** – i.e. 3.5.2, in the case of the 3.5 branch. These should generally be considered stable, but care should be taken when a minor release is being prepared.

## [Finding an SVN Client](https://make.wordpress.org/core/handbook/contribute/svn/\#finding-an-svn-client)

Most popular IDE (Integrated Developer Environment) applications include built-in support for SVN. Some also include enhanced support for WordPress development. This makes it very convenient to perform all source code version control tasks: synchronize, manage local copies, create patches, etc.

Alternatively some developers run SVN commands using the [command line interface](https://make.wordpress.org/core/glossary/#command-line-interface) (CLI), such as [Terminal](http://en.wikipedia.org/wiki/Terminal_(OS_X)) on the Mac. Even though most basic commands are simple, the command line is reasonably intimidating for many users. Many developers do rely on [GUI](http://en.wikipedia.org/wiki/GUI) applications though, either for regular use, or to handle complex actions more effectively.

When not using an IDE, or if a stand-alone GUI application is required, for Windows the recommended SVN client is [TortoiseSVN](http://tortoisesvn.net/), which is free and open source.

For Mac, the recommended SVN client is [Cornerstone](http://www.zennaware.com/cornerstone/), which must be purchased.

## [Learn More](https://make.wordpress.org/core/handbook/contribute/svn/\#learn-more)

If you would like to learn more about working with Subversion, check out [Installing A Version Control System](https://make.wordpress.org/core/handbook/tutorials/installing-a-vcs/), [Installing WordPress Via SVN](https://make.wordpress.org/core/handbook/tutorials/installing-wordpress-locally/from-svn/), and [Working With Patches](https://make.wordpress.org/core/handbook/working-with-patches/) in the **Tutorials and Guides** section of this handbook.

First published

December 13, 2011

Last updated

November 19, 2019

## 6 responses to “The Code Repository (SVN)”

1. ![Russell Heimlich Avatar](https://secure.gravatar.com/avatar/b523a37c0496cd23d8c8780e5266a42f2aad4f7f8bfacfa2dbb72bfa6d7f12ca?s=40&d=mm&r=g)







[Russell Heimlich](http://www.russellheimlich.com/blog/)





[April 11, 2013](https://make.wordpress.org/core/handbook/contribute/svn/#comment-8694)







For a free cross-platform SVN GUI I use SmartSVN. They also have SmartGit which is the equivalent for Git.

2. ![Robert Dall Avatar](https://secure.gravatar.com/avatar/96555b596b7b85dc63b4e6ae6f84e7ec9efe1dc826c66c20328fccae50d99639?s=40&d=mm&r=g)







[Robert Dall](https://profiles.wordpress.org/rdall/)





[July 28, 2013](https://make.wordpress.org/core/handbook/contribute/svn/#comment-9384)







Please correct me if I am wrong but Versions can not create or apply patches… I tried a trail version of the program and couldn’t find any reference of that which made the program some what useless for the purpose of contributing to WordPress core.






1. ![Dominik Schilling (ocean90) Avatar](https://secure.gravatar.com/avatar/f35b9fb3b4afef01e3c3733a23e362a12a7122cbe6e78db2dc9af01336f55be8?s=40&d=mm&r=g)







      [Dominik Schilling (ocean90)](https://profiles.wordpress.org/ocean90/)





      [July 28, 2013](https://make.wordpress.org/core/handbook/contribute/svn/#comment-9385)







      That’s right. But Cornerstone can.






      1. ![Kim Parsell Avatar](https://secure.gravatar.com/avatar/8bf29c777c4a386cb938cb3afc6fa6398259c5d31103b9704f75feba84b6b385?s=40&d=mm&r=g)







         [Kim Parsell](https://profiles.wordpress.org/kpdesign/)





         [July 29, 2013](https://make.wordpress.org/core/handbook/contribute/svn/#comment-9396)







         ~~Perhaps I should remove Versions from the page, and only recommend Cornerstone as a Mac client?~~ I’ve modified the page to remove Versions.
3. ![Robert Dall Avatar](https://secure.gravatar.com/avatar/96555b596b7b85dc63b4e6ae6f84e7ec9efe1dc826c66c20328fccae50d99639?s=40&d=mm&r=g)







[Robert Dall](https://profiles.wordpress.org/rdall/)





[July 28, 2013](https://make.wordpress.org/core/handbook/contribute/svn/#comment-9394)







Pardon my curmudgeon comment, but should we mention a svn client that doesn’t work with our current workflow?

4. ![adragos Avatar](https://secure.gravatar.com/avatar/e9bfa774765eed05763c050a7e7cc2ee8d576d1d8d6351b5efbb19545d9ad277?s=40&d=mm&r=g)







[adragos](https://profiles.wordpress.org/adragos/)





[August 2, 2013](https://make.wordpress.org/core/handbook/contribute/svn/#comment-9431)







Eclipse (and Eclipse based PHP Editor) has a pretty neat SVN GUI.


PhpStorm (which is not free but it’s worth paying for) also have a cool SVN/Git GUI


[PreviousThe WordPress CodebasePrevious: The WordPress Codebase](https://make.wordpress.org/core/handbook/contribute/codebase/)

[NextResearching Code HistoryNext: Researching Code History](https://make.wordpress.org/core/handbook/contribute/svn/code-history/)

[WordPress.org](https://wordpress.org/)[WordPress.org](https://wordpress.org/)

- [Visit our X (formerly Twitter) account](https://www.x.com/WordPress)
- [Visit our Bluesky account](https://bsky.app/profile/wordpress.org)
- [Visit our Mastodon account](https://mastodon.world/@WordPress)
- [Visit our Threads account](https://www.threads.net/@wordpress)
- [Visit our Facebook page](https://www.facebook.com/WordPress/)
- [Visit our Instagram account](https://www.instagram.com/wordpress/)
- [Visit our LinkedIn account](https://www.linkedin.com/company/wordpress)
- [Visit our TikTok account](https://www.tiktok.com/@wordpress)
- [Visit our YouTube channel](https://www.youtube.com/wordpress)
- [Visit our Tumblr account](https://wordpress.tumblr.com/)

![Code is Poetry](https://s.w.org/style/images/code-is-poetry-for-dark-bg.svg)

ssearchccompose new postrreplyeedittgo to topjgo to the next post or commentkgo to the previous post or commentotoggle comment visibilityesccancel edit post or comment