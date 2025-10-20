---
url: https://make.wordpress.org/core/handbook/
scraped_at: 2025-10-20T02:58:45.664Z
---

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcore%2Fhandbook%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[Skip to content](https://make.wordpress.org/core/handbook/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Make WordPress Core](https://make.wordpress.org/core)

Core Contributor Handbook

Search

# Core Contributor Handbook

## In this article

Table of Contents

- [Contribute with Testing](https://make.wordpress.org/core/handbook/#contribute-with-testing)
- [Contribute with Code](https://make.wordpress.org/core/handbook/#contribute-with-code)
- [Best Practices](https://make.wordpress.org/core/handbook/#best-practices)
- [Tutorials & Guides](https://make.wordpress.org/core/handbook/#tutorials-guides)
- [Need help?](https://make.wordpress.org/core/handbook/#need-help)

[↑ Back to top](https://make.wordpress.org/core/handbook/#wp--skip-link--target)

Welcome to the Core Contributor Handbook, the place to learn how to get involved with the WordPress core development community, and start contributing to WordPress core.

Whether you are a beta tester, casual contributor, or serious contributor, this handbook will provide the information you need to get started.

Here you can learn about how the WordPress project is organized, communication channels, best practices, the Trac workflow process, and more. There are also guides to help you set up the tools you’ll need to start contributing to WordPress core.

## [Contribute with Testing](https://make.wordpress.org/core/handbook/\#contribute-with-testing)

Testing is a very important part of the release cycle. You can install the latest development version locally to test new features, and how the changes work with your site setup (theme/plugins/etc.). You can [start testing](https://make.wordpress.org/core/handbook/testing/) as soon as a new development version is available (alpha), and continue throughout the release cycle to ensure the next version of WordPress is as bug-free as possible.

You don’t need to know how to code or create a patch, just provide a [well-written bug report](https://make.wordpress.org/core/handbook/testing/reporting-bugs/), with details of the issue and steps to reproduce. You can confirm the issue is fixed once a patch is committed and a new bleeding edge nightly version released.

Found a security vulnerability? WordPress believes in responsible and private disclosure. [Report it directly to our security team.](https://make.wordpress.org/core/handbook/testing/reporting-security-vulnerabilities/)

## [Contribute with Code](https://make.wordpress.org/core/handbook/\#contribute-with-code)

Whether you need to report one bug and provide a patch to fix it, or wish to become involved in maintaining one or more WordPress components, contributing code is a great way to improve WordPress. This section walks through [the WordPress codebase](https://make.wordpress.org/core/handbook/contribute/codebase/) and how it’s laid out, then teaches you more about [the code repository](https://make.wordpress.org/core/handbook/contribute/svn/) and [our bug tracker (Trac)](https://make.wordpress.org/core/handbook/contribute/trac/).

[Design decisions](https://make.wordpress.org/core/handbook/contribute/design-decisions/) made within WordPress are often a consideration when contributing code and are outlined in this section as well. Finally, if you’re interested in [fixing bugs](https://make.wordpress.org/core/handbook/contribute/fixing-bugs/), our walkthrough is made to get you quickly started.

## [Best Practices](https://make.wordpress.org/core/handbook/\#best-practices)

Over time, the WordPress community has developed some [best practices](https://make.wordpress.org/core/handbook/best-practices/), which keep the code base consistent and understandable by the community.

In the best practices section, we outline the [coding standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/) for [CSS](https://make.wordpress.org/core/handbook/best-practices/coding-standards/css/), [HTML](https://make.wordpress.org/core/handbook/best-practices/coding-standards/html/), [JavaScript](https://make.wordpress.org/core/handbook/best-practices/coding-standards/javascript/), and [PHP](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/). Additionally, [inline documentation standards](https://make.wordpress.org/core/handbook/best-practices/inline-documentation-standards/) for both [JavaScript](https://make.wordpress.org/core/handbook/best-practices/inline-documentation-standards/javascript/) and [PHP](https://make.wordpress.org/core/handbook/best-practices/inline-documentation-standards/php/) are documented in-depth.

Finally, the section walks through the [Core APIs](https://make.wordpress.org/core/handbook/best-practices/core-apis/) and the best practices to follow when [writing patches](https://make.wordpress.org/core/handbook/best-practices/writing-patches/).

## [Tutorials & Guides](https://make.wordpress.org/core/handbook/\#tutorials-guides)

Completely new to WordPress development? In this section, we include a number of [tutorials and guides](https://make.wordpress.org/core/handbook/tutorials/) to help get you setup. Whether you want to [setup WordPress for local development](https://make.wordpress.org/core/handbook/tutorials/installing-wordpress-locally/), [install a local server](https://make.wordpress.org/core/handbook/tutorials/installing-a-local-server/), [install a version control system (VCS)](https://make.wordpress.org/core/handbook/tutorials/installing-a-vcs/), understand how to [work with patches](https://make.wordpress.org/core/handbook/tutorials/working-with-patches/), or better understand how to [work with Trac](https://make.wordpress.org/core/handbook/tutorials/trac/), we have you covered.

## [Need help?](https://make.wordpress.org/core/handbook/\#need-help)

We all start somewhere. If you’re having trouble getting involved with contributing to WordPress core, come find us on [Slack](https://chat.wordpress.org/) in #core. We don’t bite. 😊

If you’re interested in improving this handbook, leave a message in #core-docs.

First published

December 13, 2011

Last updated

March 28, 2018

## 9 responses to “Core Contributor Handbook”

1. ![Siobhan Avatar](https://secure.gravatar.com/avatar/c960c87e0de50b310704d4b2aa94017167a292725c1744db04c781366eb6d280?s=40&d=mm&r=g)







[Siobhan](http://wordsforwp.com/)





[August 6, 2012](https://make.wordpress.org/core/handbook/#comment-8698)







Hi guys – am going to read through some of the manual today and come up with some thoughts/comments etc. I can’t believe how much has been added since yesterday – can see everyone was working really hard. Wish I could have been in SF but was in rainy England 🙁



Anyway, at the risk of stepping on toes, I’ll add some thoughts – I hope they’re useful. If you guys discussed any of it yesterday tell me to stfu.



First things first – the landing page is a bit confusing. Title is “Core Contributor Handbook” and underneath it says “Howdy! This is a rough draft of the handbook for contributing to WordPress.” So I’m not 100% sure if the handbook is just for core, or for more general contributions.



My own feeling is to keep it for core (I think that’s the intention, right?) but to have a clear notice somewhere that says “Can’t Code? Check out These Other Ways to Contribute” – this could link to a list of the other handbooks (and the theme could be carried across the handbooks to direct people to the right place). Am assuming that there will be other handbooks – that would be fantastic. I can see a handbook for writing the Codex being really useful – also for all of the other contributor groups.



So, back to the CCH: that top line can be remedied by changing it to: “”Howdy! This is a rough draft of the handbook for contributing to WordPress core.”



Believe it or not, I tried to contribute to core a few weeks ago myself. I was chatting to [@duck\_](https://profiles.wordpress.org/duck_/) at WordCamp Edinburgh and he was saying that there is a massive list of documentation errors: [https://core.trac.wordpress.org/ticket/20425](https://core.trac.wordpress.org/ticket/20425) So I thought that this was something I could take a look at. Anyway, I tried to figure out what to do, but I failed, mostly because I wasn’t sure about where to get started. What I thought would be really useful for people like me, (and for people who can actually write code) was a “First Steps” Guide. An off-the-top-of-my-head sketch of how this would look was:



1\. Requirements (the level of knowledge required (with links to places where people can learn more should they not have the required level), what’s expected, any software that is needed)



2\. Essential reading (the absolute essentials that someone needs to read before contributing. Or even a bulletpointed list of the essential things that someone needs to know)



3\. Setting up your dev environment (with links to tutorials on how to set up MAMP, XAMPP etc)



4\. Setting up Subversion



5\. Creating your first patch (with a link to coding standards)



6\. Available patches (would it be possible to generate a list of things that need to be done, and tag them so they appear under different headings e.g. beginner PHP, advanced PHP, CSS, Docs, etc etc)



7\. Learn More & Getting Help (links to more things that need to be read)



For an absolute beginner like me that would be really helpful in telling me exactly what I need to do. In fact, this sort of “First Steps” guide could be replicated across the manuals, so in each manual there is consistency






1. ![Siobhan Avatar](https://secure.gravatar.com/avatar/c960c87e0de50b310704d4b2aa94017167a292725c1744db04c781366eb6d280?s=40&d=mm&r=g)







      [Siobhan](http://wordsforwp.com/)





      [August 6, 2012](https://make.wordpress.org/core/handbook/#comment-8699)







      this is definitely the beginnings of what I was thinking re: first steps guide: [https://make.wordpress.org/core/handbook/submitting-a-patch/](https://make.wordpress.org/core/handbook/submitting-a-patch/)

2. ![Ipstenu (Mika Epstein) Avatar](https://secure.gravatar.com/avatar/b7ad69111b920f12182a57051bfe7bed2f61725588c47b4bdaff0c95c6e712f9?s=40&d=mm&r=g)







      [Ipstenu (Mika Epstein)](http://halfelf.org/)





      [August 8, 2012](https://make.wordpress.org/core/handbook/#comment-8700)







      Contributing to core doesn’t mean you have to know how to code, though.



      UI is part of core. As is accessibility, documentation, the help screens, etc etc 🙂 So part of learning how to contribute to core is learning where _you_ best fit. That’s why @hanni and I put things in the order. We’re assuming people start at 0 – what’s going on here? and move on to 10 – re-writing ms-files.php
2. ![palimadra Avatar](https://secure.gravatar.com/avatar/37fa1000bc6cc242ef265fc95d7a2527938fb382f800d646b51b9c61f22d6899?s=40&d=mm&r=g)







[palimadra](http://www.palimadra.tumblr.com/)





[August 14, 2012](https://make.wordpress.org/core/handbook/#comment-8701)







Hello,



Sorry for the n00b question.



What is the best way to get in contact with a WordPress core developer to request access to the site so that I can contribute to [https://make.wordpress.org/core/handbook/coding-standards/](https://make.wordpress.org/core/handbook/coding-standards/). I will be able to give about 10 hours a week to WordPress. I wanted to know the right etiquette so that I do not piss anyone off. I thought about using Twitter but then decided to ask the community to help.

3. ![Ze Fontainhas Avatar](https://secure.gravatar.com/avatar/d71843bd2670ce03308e7ab56b82febe090a6cfb9944e81657bd619a4756d50f?s=40&d=mm&r=g)







[Ze Fontainhas](http://wp-portugal.com/)





[September 10, 2012](https://make.wordpress.org/core/handbook/#comment-8707)







I’d like to start contributing and editing, particularly on the localization sections. I’m happy to start by adapting and adding this:



[http://wprealm.com/blog/translate-wordpress-part-i-getting-started-and-adding-support-for-a-language/](http://wprealm.com/blog/translate-wordpress-part-i-getting-started-and-adding-support-for-a-language/)

4. ![Isaac Keyet Avatar](https://secure.gravatar.com/avatar/22cadb62dfe01149e69cd75d928048b65b2d55b4309ef8eee63e61741b554f40?s=40&d=mm&r=g)







[Isaac Keyet](http://isaackeyet.com/blog)





[March 12, 2013](https://make.wordpress.org/core/handbook/#comment-8710)







I came here looking for tips on how to disable WP loading the minified CSS/JS by default, without finding anything specific. This was the section I primarily looked at:



[https://make.wordpress.org/core/handbook/the-wordpress-codebase/#javascript-css](https://make.wordpress.org/core/handbook/the-wordpress-codebase/#javascript-css)



It would seem as if almost every designer working on core CSS would need to apply this in their wp-config to have their changes show up immediately:



define(‘SCRIPT\_DEBUG’, true);



I’m pretty sure this is mentioned somewhere else in the handbook, but given that this is something that almost every contributor will run into it might make sense to make it more prominent (and perhaps link to it directly from the section above).






1. ![Siobhan Avatar](https://secure.gravatar.com/avatar/1717fc8a0f220af1621d495b085ab9d908285a8263303be0cf308bebc30dcd88?s=40&d=mm&r=g)







      [Siobhan](http://wordsforwp.com/)





      [March 13, 2013](https://make.wordpress.org/core/handbook/#comment-8711)







      Are there other things that a designer (or developer) should always do when they start working on patches? This could warrant a tutorial: something along the lines of “How to Set Up WordPress to Work on Core” – could include:



      a) turn on script debugging



      b) something else



      c) something else



      Is that something that would be useful?






      1. ![J.D. Grimes Avatar](https://secure.gravatar.com/avatar/742b3338e556c23bec91704af5f7a67b2634822278688e955b7a720eed98ec4f?s=40&d=mm&r=g)







         [J.D. Grimes](http://efieldguide.com/)





         [March 19, 2013](https://make.wordpress.org/core/handbook/#comment-8712)







         I think a tutorial on that would definitely be useful. I’ve never contributed to core, but if I did, I would start by looking for such a tutorial.

      2. ![Terry Sutton Avatar](https://secure.gravatar.com/avatar/2ab09d30033d6da9bbb7533e5302781401279c37c543e2e35d2b9d95ae1400c7?s=40&d=mm&r=g)







         [Terry Sutton](http://waterstreetgm.org/)





         [March 28, 2013](https://make.wordpress.org/core/handbook/#comment-8713)







         I’d find this very useful. Questions like this, to be more specific:



         1\. I want to work on ticket x. It has 10 diffs on it already. Where do I start?



         2\. What is a diff? Is it a patch? How do I download a patch? How do I apply the patch?



         3\. How can I undo a patch?



         4\. How do I make my own patch?



         5\. Now that I’ve made all these changes, my repo is now completely out of sync. What now?



         5\. Can I manage this workflow with git?



         I think it would be really helpful to walk through that workflow ��ie: coming into an ticket that’s well underway.

[NextAboutNext: About](https://make.wordpress.org/core/handbook/about/)

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