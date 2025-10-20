---
url: https://make.wordpress.org/core/handbook/testing/reporting-bugs/
scraped_at: 2025-10-20T02:59:35.921Z
---

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcore%2Fhandbook%2Ftesting%2Freporting-bugs%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[Skip to content](https://make.wordpress.org/core/handbook/testing/reporting-bugs/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Make WordPress Core](https://make.wordpress.org/core)

Reporting Bugs

[Home](https://make.wordpress.org/core)[Handbook](https://make.wordpress.org/core/handbook/)[Contribute with Testing](https://make.wordpress.org/core/handbook/testing/)Reporting Bugs

Search

# Reporting Bugs

## In this article

Table of Contents

- [Reporting Security Issues](https://make.wordpress.org/core/handbook/testing/reporting-bugs/#reporting-security-issues)
- [Overview of Bug Reporting and Resolution](https://make.wordpress.org/core/handbook/testing/reporting-bugs/#overview-of-bug-reporting-and-resolution)
- [Before You Report a Bug](https://make.wordpress.org/core/handbook/testing/reporting-bugs/#before-you-report-a-bug)
- [Reporting a Bug](https://make.wordpress.org/core/handbook/testing/reporting-bugs/#reporting-a-bug)

[↑ Back to top](https://make.wordpress.org/core/handbook/testing/reporting-bugs/#wp--skip-link--target)

## [Reporting Security Issues](https://make.wordpress.org/core/handbook/testing/reporting-bugs/\#reporting-security-issues)

While we try to be proactive in preventing security problems, we do not assume they’ll never come up. If you believe you’ve found a security problem in a release of WordPress, please see the [Security FAQ](https://make.wordpress.org/core/handbook/reporting-security-vulnerabilities/) for information on how to report the problem.

It is standard practice to notify the vendor (the WordPress security team, in this case) of a security problem before publicizing, so a fix can be prepared, and public damage due to the vulnerability minimized.

## [Overview of Bug Reporting and Resolution](https://make.wordpress.org/core/handbook/testing/reporting-bugs/\#overview-of-bug-reporting-and-resolution)

There are many steps in the process of reporting and resolving a bug in WordPress. Here is an overview:

- A user finds a bug that appears to be in the core of WordPress (not a theme or a plugin).
- The user confirms it is actually a bug which has not yet been reported.
- The user submits a bug report, called a [ticket](https://make.wordpress.org/core/handbook/glossary/#ticket), to [Trac, the WordPress Bug Tracker](https://make.wordpress.org/core/handbook/trac/).
- A WordPress developer (who is a volunteer, like you) confirms that the bug does actually exist, and that it should be fixed, and comments as such.
- A WordPress developer (which could be you) decides to fix the bug. The developer figures out how to fix the bug, create a patch, and uploads the patch to Trac.
- Members of the WordPress development community test the patch to see if it fixes the bug, and doesn’t break anything else. They may also run [Automated Tests](https://make.wordpress.org/core/handbook/automated-testing/) against the bug and patch, and write new tests (or suggest new tests be written).
- One of the WordPress developers with authority to modify the official WordPress source code [commits](https://make.wordpress.org/core/handbook/glossary/#commit-verb) the patch to the core code in the SVN repository. They are more likely to do this if the bug and patch has been verified by someone they trust – WordPress development operates largely on a system of trust and merit.
- The person who commits the patch closes the bug as **fixed**.

## [Before You Report a Bug](https://make.wordpress.org/core/handbook/testing/reporting-bugs/\#before-you-report-a-bug)

With large projects like WordPress, so many users report bugs that there’s a good chance your bug has already been reported. Because of this, it’s very important to check to ensure it’s not already in the system before you submit it. If you are new to reporting bugs in WordPress, it is also a good idea to discuss the issue with more experienced developers before reporting it.

**1\. Make sure the bug is actually caused by WordPress core.**

Just because an error message points to a core file, doesn’t mean that’s where the problem is. You may want to use a plugin like [Debug Bar](https://wordpress.org/extend/plugins/debug-bar/) to track down the problem. A simple script like this [debugging file](http://gist.github.com/625769) could help you see where exactly the error is coming from. (You can place this file in your **wp-content/mu-plugins** directory; create it if it doesn’t exist.)

Another key strategy is to try and replicate the bug in a fresh WordPress install with no extra plugins or themes. While this may not always be possible, if you can find it in a fresh install, the issue is much more likely to be in core.

**2\. [Search](https://core.trac.wordpress.org/search) for your bug or enhancement request.**

- If your issue has already been reported, please do not report a duplicate bug. If you have further information to contribute, add a note to the existing bug.
- If your issue is similar, but not quite the same as another issue, you may decide whether to add a note to the similar issue, or report a new one. In general, if you just have more information to contribute to a current, open issue, simply add a note to that issue. If you have a different enough issue, or if you are experiencing a recurrence of an issue that was previously resolved, report a new bug. Either way, core contributors will offer you guidance once you’ve posted about your issue.
- If your issue was recently reported and then closed, and you do not agree with the resolution, you can still post comments as to your reasoning.
- It is best not to re-open bugs that have been closed for some time. If the bug was closed as **fixed** for a version of WordPress that has been released already (see the **Milestone** field), open a new ticket.
- The **Version** field relates to the version in which the bug was originally discovered. If you’re seeing the same bug in a newer version, mention so in a comment, but please do not change the version number.

**3\. Consider discussing a possible bug before reporting it.**

- If you aren’t sure that you’ve found a bug, you should attempt to discuss it with a developer before reporting it. You can discuss your issue on the [WordPress Slack Channel](https://make.wordpress.org/chat/), post a question on the [WordPress Support Forum](https://wordpress.org/support/), or start an email discussion on the [wp-testers](https://codex.wordpress.org/Mailing_Lists#Testers) or [wp-hackers](https://codex.wordpress.org/Mailing_Lists#Hackers) mailing lists.

## [Reporting a Bug](https://make.wordpress.org/core/handbook/testing/reporting-bugs/\#reporting-a-bug)

Trac is the name of the official WordPress bug tracker. It uses the open source bug tracking software Trac, by Edgewall Software. To learn more about Trac, see [The Bug Tracker (Trac)](https://make.wordpress.org/core/handbook/trac/). To create a good bug report:

1. Read the section above about what to do [before reporting a bug](https://make.wordpress.org/core/handbook/testing/reporting-bugs/#before-you-report-a-bug).
2. Log onto [WordPress Trac](https://core.trac.wordpress.org/) using your [support forum](https://wordpress.org/support/) username and password. If you don’t have an account at the support forums, you can [register](https://wordpress.org/support/register.php).
3. Click [New Ticket](https://core.trac.wordpress.org/newticket) in Trac to reach the bug reporting page.
4. Fill in the title, summary, and other fields. For more, see the section on [Ticket Properties](https://make.wordpress.org/core/handbook/trac/#ticket-properties).
5. Click **Submit Ticket** after previewing it.

Your involvement doesn’t end after you’ve submitted a ticket. Developers may need more information as they review the ticket (and may specifically request more information from you by tagging the ticket with **reporter-feedback**).

You can also help by verifying that proposed fixes solve the problem you were experiencing. The processing of your bug may require your participation, so please be willing and prepared to aid the developers in resolving the issue. If you’d like to help fix the bug, see the section on [Fixing Bugs](https://make.wordpress.org/core/handbook/fixing-bugs/).

You will be automatically emailed when your tickets are updated if you’ve entered your email address in [your Trac preferences](https://core.trac.wordpress.org/prefs).

First published

December 14, 2011

Last updated

September 18, 2015

[PreviousUsabilityPrevious: Usability](https://make.wordpress.org/core/handbook/testing/user-testing/usability/)

[NextReporting Security VulnerabilitiesNext: Reporting Security Vulnerabilities](https://make.wordpress.org/core/handbook/testing/reporting-security-vulnerabilities/)

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