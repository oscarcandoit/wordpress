---
url: https://www.php.net/manual/en/security.general.php
scraped_at: 2025-10-20T02:39:00.239Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# General considerations [¶](https://www.php.net/manual/en/security.general.php\#security.general)

A completely secure system is a virtual impossibility, so an
approach often used in the security profession is one of balancing
risk and usability. If every variable submitted by a user required
two forms of biometric validation (such as a retinal scan and a
fingerprint), you would have an extremely high level of
accountability. It would also take half an hour to fill out a fairly
complex form, which would tend to encourage users to find ways of
bypassing the security.


The best security is often unobtrusive enough to suit the
requirements without the user being prevented from accomplishing
their work, or over-burdening the code author with excessive
complexity. Indeed, some security attacks are merely exploits of
this kind of overly built security, which tends to erode over time.


A phrase worth remembering: A system is only as good as the weakest
link in a chain. If all transactions are heavily logged based on
time, location, transaction type, etc. but the user is only
verified based on a single cookie, the validity of tying the users
to the transaction log is severely weakened.


When testing, keep in mind that you will not be able to test all
possibilities for even the simplest of pages. The input you
may expect will be completely unrelated to the input given by
a disgruntled employee, a cracker with months of time on their
hands, or a housecat walking across the keyboard. This is why it's
best to look at the code from a logical perspective, to discern
where unexpected data can be introduced, and then follow how it is
modified, reduced, or amplified.


The Internet is filled with people trying to make a name for
themselves by breaking your code, crashing your site, posting
inappropriate content, and otherwise making your day interesting.
It doesn't matter if you have a small or large site, you are
a target by simply being online, by having a server that can be
connected to. Many cracking programs do not discern by size, they
simply trawl massive IP blocks looking for victims. Try not to
become one.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/security/general.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsecurity.general%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.general&repo=en&redirect=https://www.php.net/manual/en/security.general.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google