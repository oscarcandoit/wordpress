---
url: https://make.wordpress.org/plugins/
scraped_at: 2025-10-20T03:01:05.635Z
---

[Skip to content](https://make.wordpress.org/plugins/#primary)

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fplugins%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[WordPress.org](https://wordpress.org/)

# [Make WordPress Plugins](https://make.wordpress.org/plugins)

[**Menu**](https://make.wordpress.org/plugins/#)

Hide welcome box

### Welcome to the official blog for the Plugins Team.

The team acts as gate-keepers and fresh eyes on newly submitted plugins, as well as reviewing any reported security or guideline violations.

**Quick Links**

- [Handbook](https://make.wordpress.org/plugins/handbook)
- [Reporting Plugin Issues](https://developer.wordpress.org/plugins/wordpress-org/plugin-security/reporting-plugin-security-issues/)
- [Plugin Developer Resources](https://developer.wordpress.org/plugins/)
- [Plugin Directory Resources](https://developer.wordpress.org/plugins/wordpress-org/)

### Communication

We can be reached by email at **plugins＠wordpress.org**, or via the [**#pluginreview**](https://wordpress.slack.com/messages/pluginreview) channel on [Slack](https://make.wordpress.org/chat/).

After WordCamp US, we have prepared some insights about our team and we wanted to share it with the community.

These are the insights from the Plugins Team:

- We now have **60,187 plugins** published in the directory.
- Today, we received as many new plugins and completed as many reviews as we did in the entire last year.
- We have received **7,670 new submissions** this year, which is **87.3% more** than in the same period last year.
- Since the start of the year, we have had an average of 235 new submissions per week. In the same period last year, there were 124 new plugins.
- The queue is less than one week, even though we have received many more submissions.
- On average, we spend **6.19 review cycles** to approve a plugin, which is **11.2% fewer reviews per plugin** compared to last year.
- 85.3% of first reviews made this year were initiated by an automated system that uses algorithms and AI to perform the first review of the plugin, requiring only minimal input from human reviewers, saving us time.
- **64.2%** of plugin authors successfully engaged with the review process, which is **17.1% higher** than the year before.
- Out of the plugin authors that followed the review process, 60.27% were approved.

**In summary**, although the number of submitted plugins is increasing, the team’s effort remains steady, thanks in part to AI automation in certain areas. Our goal is to continue improving by implementing AI in more checks, as well as introducing proactive scanning of the current Plugins Directory.

_All this data was prepared on the 31th of August._

Written by [@davidperez](https://profiles.wordpress.org/davidperez/), reviewed by [@frantorres](https://profiles.wordpress.org/frantorres/)

As developers, the PCP Checker Plugin has been a huge help in identifying and fixing issues before submission. It has completely transformed our plugin submission process.”

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fplugins%2F2025%2F08%2F31%2Fstats-of-plugins-team-after-wordcamp-us%2F%23comment-44462&locale=en_US)

+1 👍 Indeed I discovered the PCP checker plugin this year and it’s a really great companion to produce code more compliant with the WordPress framework. Thanks a lot for that 🤲

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fplugins%2F2025%2F08%2F31%2Fstats-of-plugins-team-after-wordcamp-us%2F%23comment-44464&locale=en_US)

**In summary:** You are AWESOME and you are doing a great job, nice collaboration and wonderful team work 😍 Keep up and don’t hurt yourself with a PHP bracket 😉

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fplugins%2F2025%2F08%2F31%2Fstats-of-plugins-team-after-wordcamp-us%2F%23comment-44465&locale=en_US)

Plugin Upload Precheck helped me to rectify in plugin upload issue.

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fplugins%2F2025%2F08%2F31%2Fstats-of-plugins-team-after-wordcamp-us%2F%23comment-44466&locale=en_US)

Through [#8009-meta](https://meta.trac.wordpress.org/ticket/8009) we’ve started work on adding Phased / Staged plugin releases to plugins utilising Release Confirmation.

**What is phased releases?** In short, this allows for your plugin update to be released to a smaller subset of sites prior to full release to all sites.

**Why would you want to use it?** Sometimes plugin updates can inadvertently break user workflows or run into conflicts with other plugins. Often these issues are not known until after a plugin update is released, and lots of users have already installed the update, this allows for a short timeframe where hopefully engaged users will report issues to you sooner.

**How?** Initially this has been limited to plugins using **Release confirmations**. This means a plugin has to explicitly **opt-in** to using this feature at the time of the plugin’s update release.

To start with, only one strategy is offered, **Delay Auto-updates for 24 hours** – This disables the WordPress plugin automatic updates for the first 24 hours of a plugin release. Site Administrators can still click on “Update” to install the latest version, as it’s hoped that these users would spot any issues that result from using the updated version.

[![Release Confirmation showing a rollout strategy selection.](https://make.wordpress.org/plugins/files/2025/08/release-confirmation-rollout-strat-1024x312.png)](https://make.wordpress.org/plugins/files/2025/08/release-confirmation-rollout-strat.png) Example of the Rollout Strategy selection included in Release Confirmations.

**Technical Limitations**

1. To ease the potential of user confusion, this has been initially launched focusing on disabling automatic updates, rather than disabling the update entirely for a WordPress site.
2. Currently WordPress.org can only instruct WordPress 6.6+ sites not to automatically update the plugin.
3. Currently WordPress.org can track the number of plugin updates _(Through the Active installs / Active versions statistics)_, but can’t differentiate between a user-initiated/manual update and an automatic update.
4. It’s up to 3rd-party update tooling to [respect the WordPress 6.6+ flag to disable automatic updates](https://core.trac.wordpress.org/ticket/52796), it’s unknown whether any of these tools respect it. Anything that runs the WordPress Automatic updater _should_ support it.

**What will future iterations bring?**

What functionality is offered here will heavily depend upon author feedback in using the feature, or what would encourage them to do so. Examples of what this could be include..

- Strategies that rollout updates to a percentage of sites. For example, 1% per hour, or gradually increasing to 20% over 3 days and the final 80% on day 4.
- Improvements to find out if there’s been any issues reported in the update. For example:
  - Are plugin reviews overly negative?
  - Have any PHP Warnings/Fatal errors been reported automatically (not implemented)
  - Have WordPress updates been rolling back to their previous version (in the cases of fatal errors)
- Statistics of how many sites have updated to the new version. Could be a rounded number (like the existing Active Installs) or simply a percentage (like the Active Versions chart). Eg: Plugin: 100k Active installs; Latest version: 80k+ or 80%.

**Questions for Plugin Authors**

- **Do you plan to use this feature?** If not, What would convince you to?
- **What improvements would you like to see?**

For example: What strategies? What additional information? What would tell you your plugin update is a success?
- **Would you like to see manual/user-initiated update availability also disabled?**

_Thank you to the handful of plugin authors who have already made use of this feature._

_Edits: An image of the UI added a few hours later._

This would be an excellent tool! Rolling out the update to just 10-20% of the sites in the first 24-48 hours is a good strategy to decrease breaking updates.

Maybe admins could also have an option to “enable rollout/beta” auto-updates. On the other hand this might end up filling up the % of rollout websites without any actual feedback.

Also, maybe plugin authors should have a way to flag “non-reversible” updates (that make database or file changes) where you can’t just drop back to the previous version and you **should** backup your website before.

> an option to “enable rollout/beta” auto-updates.

Importantly, It should be noted that these releases are **not beta** versions, it’s intended that this is a final/stable release. A beta release is designed to “not be for production use and may have bugs”.

> this might end up filling up the % of rollout websites without any actual feedback.

That’s my thought. For example, if a plugin adds a Block to the editor, and the site owner publishes every Wednesday and Saturday, but the update came out on a Sunday, they’re not going to notice the broken behaviour until they attempt to publish on Wednesday.

Whereas, if the site owner saw an update and installed it on Monday, they’re more likely to then check that their site is still operational and that the Block works.

Very good idea, only allowing auto-update sites to see updates in first 24 hours is a great start and likely good enough for most of us. Albeit, many of those auto-update sites will not be actively monitored by their owners, nevertheless it will allow for some feedback if an update breaks things.

Having the ability to enable phased releases from the Release Confirmation UI would be great.

From the other side of the fence, sometimes a plugin update triggers some work for site maintainers and the preference is to get that over and done with across all relevant sites. I see this with Gravity Forms updates, a plugin that already supports phased releases. I notice the update on one or more sites, download the update and check to see what impact it will have. If there’s, say, styling fixes to be made, I’ll want to be able to churn through affected sites straight away. With Gravity Forms, one can force the release check by visiting the system status page, so I can update all sites whether or not they saw the phased release.

I don’t know whether that can be accommodated through the “Check again” link on the WordPress Updates page, but it could be handy if it’s possible.

> many of those auto-update sites will not be actively monitored by their owners

I think you’ve misread it, currently the option offered is “do NOT auto-update” for 24hrs, such that initial updates are going to be from users who are maintaining / using their site at time of update.

> one can force the release check by visiting the system status page, so I can update all sites whether or not they saw the phased release.

This is why I’ve started with only _disabling auto-updates_ to start with, if a release fixes a bug that a site owner has been experiencing, I want them to be able to immediately install that update on all their sites.

I feel that a user seeing an update available on WordPress.org, and in SiteA but not in SiteB would cause confusion.

Sorry, yes, I had it straight in my head on first reading, but {{the usual distractions}} meant that it somehow flipped. Good, good!

If the phased release mechanism later evolves to offer percentages of websites the release, it would be handy to force getting the release notification via “Check again” if that’s possible.

> it would be handy to force getting the release notification via “Check again” if that’s possible

That’s a reasonable workaround! At present it’s not possible, but a minor modification to core could be made to make it work.

Staged roll out great idea, I’d like to set the length of the rollout, users should be able to manually update and perhaps set how much risk they are willing to take with updates like Microsoft does (be first or lastish)

> I’d like to set the length of the rollout

[@dbareis](https://profiles.wordpress.org/dbareis/) What kind of length of time do you think you’d want to use? And in what shape, Just disabling automatic updates for X days (1? 2? 3?), a constant increase (ie. 1% per hour), or a logarithmic (eg 25% over the first 3 days, the remaining 75% over the next day)?

Slow start rollout over maybe 2 weeks

Wow ! Great idea, yes would use it.

Those who update manually tend to be the ones who will a) update early, b) know what updates they have done, c) look at what the plugin fixes/adds and test that

They are the ones that report issues to me typically within a day, so that would mean I can iron out any issues before the majority get the update.

Yes, I will use whatever you guys come up with. It’s a great idea to limit the blast radius of a broken plugin update. Thanks.

My only suggestion? Keep it simple and easy to understand.

Do you plan to use this feature? Yes

What improvements would you like to see? None at this stage. Looks OK for an initial trial.

Would you like to see manual/user-initiated update availability also disabled? No.

This is fantastic Dion [@dd32](https://profiles.wordpress.org/dd32/)!

We will definitely make use of this, especially on our plugins that have a larger active install base. We were actually just discussing this internally yesterday so I was surprised to see this post!

I think giving the committer ability to configure the %ages for the rollout would be handy. For example, most often we would just set 20% on day 1 and the remaining 80% on day 3 to make sure things are stable for a full 24hr period (accounting for timezones) before rolling out the entire release.

Another request, and I’m not sure if this is something that would be considered since active install exact counts are private currently, but being able to see how many people on each version would be amazing. If thats not possible, seeing how many people out of the % set have actually updated would be a great second.

I would love to see this addition. Something that would make it more appealing to me would be the ability to invite specific users to upgrade. This would allow for granular control over the release without having to install the plugin manually via zip.

This is a really exciting development! Thank you to everyone who has been working on it. Gradual rollouts will be a huge step forward for plugin stability and user trust, and we’re very appreciative of the effort that’s gone into making this possible.

From the perspective of a large-scale plugin like Elementor, we wanted to share a couple of thoughts. In the current design, only plugin committers/admins can manage these phased releases. For security reasons, we keep that group very small, which means every release would need to be funneled through just a couple of people. That creates a bottleneck that makes it difficult for us to realistically use this otherwise great feature.

One idea that could help would be to introduce a dedicated role, such as “Release Manager,” who would have the specific ability to create and manage phased rollouts, without having the broader and higher-risk permissions that committers have (like deleting plugins).

Additionally, it could be very valuable if release managers had the ability to stop or freeze a rollout during the 24-hour timer window. This would give teams a chance to pause a release mid-rollout if issues surface, before it reaches all users.

We’re really grateful for the work being done here, and we hope this perspective from the large-plugin side is helpful as the feature evolves.

Every day, we review a significant number of plugins, and since last year, [we have been receiving many more requests each week](https://make.wordpress.org/plugins/2025/05/21/the-wordpress-ecosystem-is-growing-new-plugin-submissions-have-doubled-in-2025/). In addition, our team is made up of a diverse group with different languages and alphabets.

For this reason, **our team uses English as the official language within the community and for communication with authors during the review process**.

As part of the plugin review, we also check the `readme.txt` file, which contains all the important information about the plugin, such as its name, version, description, authors, and other relevant details. This file is essential for the management and documentation of the plugin, both for developers and users. It also serves as the basis for the plugin’s page published in the directory, which is also visible on wordpress.org/plugins/.

The plugin directory supports translations using English as the base language. Each plugin can be translated through [translate.wordpress.org](https://translate.wordpress.org/), offering versions in different languages for both the plugin information and the user interface. For more information, you can [refer to the GlotPress documentation](https://make.wordpress.org/polyglots/handbook/translating/glotpress-translate-wordpress-org/).

**From now on, we will ask authors to provide the plugin information in `readme.txt` in English.**

The main reasons for this are:

- It facilitates reviews and effective communication with the team.
- English serves as the base for translating your plugin into different languages. This ensures your plugin can be translated once it’s published.
- It unifies the Plugin Directory interface, avoiding the creation of sections in different languages and alphabets.

This decision has been agreed upon by the team with the goal of serving the general interest and making it easier to translate plugins.

Post writen by [@davidperez](https://profiles.wordpress.org/davidperez/), reviewed by [@rabmalin](https://profiles.wordpress.org/rabmalin/) and [@frantorres](https://profiles.wordpress.org/frantorres/)

Is there a specific variation of English that’s required?

No, I don’t think so.

No problem, but translation process is not an easy task. I posted translations in French for my plugin, I also asked to be a translator for it (I’m a French native speaker!), revceived answers telling me it’s OK, but after month still can get my plugin to have translations…… even mine!

Hello,

Did you explain this case to any Team Rep of Polyglots?

[https://make.wordpress.org/polyglots/](https://make.wordpress.org/polyglots/)

_I realise you said you’ve already asked for this, and been denied the status for now due to translation consistency, but I’m going to include this here for others._

If you’re a plugin author, who speaks a language (or who has employees/friends who speak a language), you can apply to have PTE (Project Translator Editor) status granted to those accounts, so they don’t require the GTE’s (Global Translator Editors – ie. for all of french) to approve translations.

This does require that you’re able to translate within the limitations that the GTE’s have specified, to ensure that the standards of translation for all users of that language are consistent. For example, with German there’s Formal & Informal, if a user has selected the Formal variant, the desire is for all plugin translations to also be in the formal variant, instead of mix-and-match.

See these guides:

- [https://make.wordpress.org/polyglots/handbook/plugin-theme-authors-guide/](https://make.wordpress.org/polyglots/handbook/plugin-theme-authors-guide/)
- [https://make.wordpress.org/polyglots/handbook/plugin-theme-authors-guide/pte-request/](https://make.wordpress.org/polyglots/handbook/plugin-theme-authors-guide/pte-request/)

Fíjate que pensaba que ya era así 😀

Me parece lógico, sobre todo porque pasa mucho que pretenden los desarrolladores que los traductores aceptemos textos “traducidos al español” desde su idioma, y sinceramente, no podemos tener traductores voluntarios desde cualquier idioma, es inviable, así que no queda otra que solo aceptar traducciones “del inglés”

Since the [team transition that took place in June 2023](https://make.wordpress.org/plugins/2023/06/29/plugin-review-team-update-the-next-phase-begins/), the goals of the Plugin Review Team have continued to grow. This change has been internally agreed upon, and we’re excited about the new name.

Here’s a quick summary of our main focus areas:

## Review of New Plugin Submissions to the Directory

This has remained our primary task and takes up most of our time. We’re [now receiving over 87% more weekly plugin submissions](https://make.wordpress.org/plugins/2025/05/21/the-wordpress-ecosystem-is-growing-new-plugin-submissions-have-doubled-in-2025/). Our goal is to keep the queue as short as possible and ensure a balanced workload across the team.

## **Improvement of Internal Tools**

The Scanner tool has undergone major upgrades, now performing over 220 automated checks on plugins. This makes the review process more efficient and reliable. We’ve also introduced AI checks for plugin names, helping ensure clear and trademark-compliant naming from the start.

## **Creation and Improvement of Community Tools**

Since **Plugin Check** Plugin [was introduced to the community](https://make.wordpress.org/plugins/2024/09/17/introducing-plugin-check-pcp/)%20(https://wordpress.org/plugins/plugin-check/), it’s become increasingly integrated into workflows, helping plugin authors self-review their plugins and boosting the overall quality and security of the WordPress ecosystem.

The team is now actively contributing to its development, adding new checks, and we’re proposing to use it during plugin updates and commits as well.

## **Improvement of the Plugin Directory**

We’ll be working closely with the Meta team to [help review open tickets](https://meta.trac.wordpress.org/query?status=!closed&component=Plugin+Directory&max=150) and propose new features we believe will improve plugin reliability and security.

We’ve come to feel that the name “Plugin Review Team” no longer reflects everything we do. That’s why we’re proposing a simplified name: “Plugins Team.” Interestingly, the [Themes Team made a similar change some time ago](https://make.wordpress.org/themes/2024/05/20/proposal-changes-to-the-themes-team/).

So we propose updating the name across various community spaces:

- **Page Title:** [https://make.wordpress.org/plugins/](https://make.wordpress.org/plugins/)
- **Mentions across wordpress.org websites**
- **Community references:** Moving forward, we kindly ask the community to refer to us as the _Plugins Team_.

We believe this small change is well deserved, given all the efforts the team has made to improve the WordPress plugin ecosystem. We’re looking forward to continuing to grow and evolve.

Post written by [@davidperez](https://profiles.wordpress.org/davidperez/), reviewed by [@frantorres](https://profiles.wordpress.org/frantorres/) and [@rabmalin](https://profiles.wordpress.org/rabmalin/)

Awesome [@davidperez](https://profiles.wordpress.org/davidperez/), [@frantorres](https://profiles.wordpress.org/frantorres/), [@rabmalin](https://profiles.wordpress.org/rabmalin/) and the entire Plugin team. You guys are doing a great job.

Thanks!!

That makes sense! Great work, everyone! Really proud of all of you.

Thanks Felipe!

It’s breathtaking to see how far you’ve gone in just a couple of years.

Thank you all for the hard work you put into the team everyday.

Wow! And there’s more coming!

[![](https://gravatar.com/avatar/f22c0ec09eb5a6df4da4239a37dbdf9d?d=mystery)](https://profiles.wordpress.org/desrosj/ "Profile of Jonathan Desrosiers (@desrosj)")

[Jonathan Desrosiers](https://profiles.wordpress.org/desrosj/ "Profile of Jonathan Desrosiers (@desrosj)") [9:58 pm on June 24, 2025](https://make.wordpress.org/plugins/2025/06/25/xpost-a-little-late-spring-cleaning/ "9:58 pm (-04:00) on June 24, 2025")

## X-comment from [+make.wordpress.org/project](https://make.wordpress.org/project/ "WordPress.org Project"): Comment on [A Little (Late) Spring Cleaning](https://make.wordpress.org/project/2025/06/25/a-little-late-spring-cleaning/\#comment-658 "Following up on the codified criteria for a repository to live under the WordPress organization on GitHub, a comprehensive audit of all repositories under both the WordPress and bbPress GitHub organizations has been conducted. To support this effort, every repository was catalogued in a spreadsheet, along with metadata to assess which met the established criteria. This includes factors such as ongoing maintenance, alignment with an active WordPress.org team or initiative, and whether the repository serves a continuing purpose. Archived Repositories In total, 20 repositories in the WordPress GitHub organization were identified as no longer meeting the criteria for active maintenance under the organization. These include: Feature plugins for projects that have already been merged into WordPr…")

[![](https://gravatar.com/avatar/d860ed93c93910d7f5c21458a3f4d190?d=mystery)](https://profiles.wordpress.org/peiraisotta/ "Profile of Isotta Peira (@peiraisotta)")

[Isotta Peira](https://profiles.wordpress.org/peiraisotta/ "Profile of Isotta Peira (@peiraisotta)") [9:06 am on June 23, 2025](https://make.wordpress.org/plugins/2025/06/23/xpost-the-incident-response-team-is-looking-for-new-members/ "9:06 am (-04:00) on June 23, 2025")

## X-comment from [+make.wordpress.org/community](https://make.wordpress.org/community/ "Make WordPress Community"): Comment on [The Incident Response Team is looking for new members](https://make.wordpress.org/community/2025/06/23/the-incident-response-team-is-looking-for-new-members/\#comment-32528 "We’re expanding the Incident Response Team (IRT) and are looking for new contributors to join us. The mission of the IRT is to provide a clear channel for community members to report and address incidents that may violate the WordPress Community Code of Conduct, ensuring a safe and respectful environment for all participants. If you’re committed to fostering a respectful community and have experience in community moderation, conflict resolution, or DEIB practices, we’d love to hear from you. Apply here You can also open the application form using the following link: https://wordpressdotorg.survey.fm/wordpress-incident-response-team-%E2%80%93-application-formApplications will remain open until July 6, 2025. Selected members will receive dedicated training and onboarding. To create more oppo…")

[![](https://gravatar.com/avatar/f22c0ec09eb5a6df4da4239a37dbdf9d?d=mystery)](https://profiles.wordpress.org/desrosj/ "Profile of Jonathan Desrosiers (@desrosj)")

[Jonathan Desrosiers](https://profiles.wordpress.org/desrosj/ "Profile of Jonathan Desrosiers (@desrosj)") [7:49 am on June 4, 2025](https://make.wordpress.org/plugins/2025/06/04/xpost-criteria-for-creating-or-migrating-repositories-under-the-wordpress-github-organization/ "7:49 am (-04:00) on June 4, 2025")

## X-comment from [+make.wordpress.org/project](https://make.wordpress.org/project/ "WordPress.org Project"): Comment on [Criteria for Creating or Migrating Repositories under the WordPress GitHub Organization](https://make.wordpress.org/project/2025/06/04/criteria-for-creating-or-migrating-repositories-under-the-wordpress-github-organization/\#comment-639 "With WordPress Core now following an annual release cadence, community-maintained canonical plugins have become even more crucial to the project. Because canonical plugins serve as official first-choice recommendations, they should live under the WordPress organization on GitHub. However, there are currently no guidelines around what is allowed or prohibited under the project’s GitHub organization. Establishing some clear criteria will help community members understand the requirements and expectations for this. Core Principles WordPress should balance experimentation with quality standards and project philosophy. GitHub repositories under WordPress should benefit the community, prevent single points of failure, and ensure open-source accessibility. Before outlining specific criteria, here…")

WordCamp Europe 2025 is coming soon and we will have several tables dedicated to the plugins team in the contributor day!

A big part of the team will be at Basel and we are ready to carry out different activities according to the interests of the community present there.

Our main topics for the contributor are:

## Plugin Check Plugin

Learn how it works and how to contribute to the project that is helping plugin authors to check their plugins for different kinds of possible issues.

Prepare for the event in advance:

- You’ll need a laptop and access to internet (there will be wi-fi and [swiss-style-plugs](https://en.wikipedia.org/wiki/SN_441011) there).
- You’ll need a WordPress local environment.
- Get familiar with the [official repository](https://github.com/WordPress/plugin-check/),
- Install it in your local environment, in the readme you have [instructions on how to download and execute it](https://github.com/WordPress/plugin-check/?tab=readme-ov-file#contributing).
- Get familiar with [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/) and best practices, as all the code need to comply with it.

## Documentation

Help out contributing to the documentation by detecting areas not covered by the current documentation and contribute suggesting changes to it.

Prepare for the event in advance:

- You’ll need a laptop and access to internet (there will be wi-fi and [swiss-style-plugs](https://en.wikipedia.org/wiki/SN_441011) there).
- Get familiar with the documentation regarding the plugins team.
  - Plugin Handbook: [Website](https://developer.wordpress.org/plugins/), [Github](https://github.com/WordPress/developer-plugins-handbook).
  - Guidelines: [Website](https://developer.wordpress.org/plugins/wordpress-org/detailed-plugin-guidelines/), [Github](https://github.com/WordPress/wporg-plugin-guidelines).
  - Reviewer’s Handbook: [Website](https://make.wordpress.org/plugins/handbook/), [Github](https://github.com/WordPress/plugins-handbook).
- Get familiar with the [basic markdown syntax](https://github.com/javiercasares/wordpress-handbook-markdown).
- Get familiar with [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/) and best practices, as documentation examples need to comply with it.

## Handbook

Learn about the best practices for developing plugins for WordPress.

Prepare for the event in advance: Gather your questions!

## General talk

Talk among the community about questions regarding the directory, how the team works, guidelines, etc.

Prepare for the event in advance: Get familiar with the [Plugin Directory Guidelines](https://developer.wordpress.org/plugins/wordpress-org/detailed-plugin-guidelines/).

* * *

We are looking forward to seeing you there!

[#contributor-day](https://make.wordpress.org/plugins/tag/contributor-day/)

We’re happy to announce that **[@davidperez](https://profiles.wordpress.org/davidperez/)** and **[@frantorres](https://profiles.wordpress.org/frantorres/)** are **stepping in as the next team reps** for the WordPress.orgPlugin Review Team!

Plugin team reps help coordinate the team’s duty, coordinate communication with the community, and ensure important updates and community activities stay on track.

**Over the past two years**, the new team has **made important progress** — incorporating new members, [reducing the plugin queue](https://make.wordpress.org/plugins/2023/09/19/update-turning-the-tide/), [creating and improving tools](https://make.wordpress.org/plugins/2024/09/17/introducing-plugin-check-pcp/), streamlining the reviews and refining processes — thanks to the collective effort of everyone involved.

Looking ahead, the team is **preparing to [tackle new challenges](https://make.wordpress.org/plugins/2025/05/21/the-wordpress-ecosystem-is-growing-new-plugin-submissions-have-doubled-in-2025/)**, which we believe will include: the impact of AI, further tool enhancements, proactive reviews, and improving documentation.

A big thank you **[to the entire team](https://make.wordpress.org/plugins/handbook/the-team/) for their dedication**, to the contributions through the “ [Five for the future](https://wordpress.org/five-for-the-future/)” program and to all **plugin authors for keeping their plugins secure, compatible, and compliant**. Together, we are evolving the WordPress plugin ecosystem!

Thanks for giving me this opportunity from this Team. Let’s make a better Directory together!

Great to see [@davidperez](https://profiles.wordpress.org/davidperez/) and [@frantorres](https://profiles.wordpress.org/frantorres/) stepping up as team reps for the Plugin Review Team! The progress over the past couple years has been solid, shorter queues, better tools, smoother reviews. Definitely feels like things are moving in the right direction.

Curious to see how they’ll handle stuff like AI, proactive reviews, and tool improvements going forward. Props to everyone who’s been contributing, and plugin devs keeping things clean and up to date, makes a big difference.

## This year, the number of plugins submitted has grown by 87% compared to last year

🌱 We have great news from the Plugins team. The submission of new plugins in WordPress has almost doubled this year, helping the WordPress ecosystem to grow.

The WordPress developer community is celebrating as they maintain and increase their submissions to be reviewed and published in the WordPress directory.

As you can see in the graph below, we detected this increase since last September, and we can observe the impact of AI as well as achievements made by the team, such as having automated tools and improvements to the internal Scanner, which, in our view, have contributed to the rise in plugin submissions to the official directory.

[![](https://make.wordpress.org/plugins/files/2025/05/new-plugins-doubled-1024x506.png)](https://make.wordpress.org/plugins/files/2025/05/new-plugins-doubled.png)

## The Rise of AI 🤖 in the Plugin Directory

🤓 It’s clear that AI is influencing plugin submissions to the directory. Here, we analyze plugins that have “AI” in their title, showing the use of Artificial Intelligence integrated into WordPress.

As seen in this chart, growth is exponential, with many plugins directly using AI to offer features within the directory.

[![](https://make.wordpress.org/plugins/files/2025/05/new-plugins-submitted-ai.png)](https://make.wordpress.org/plugins/files/2025/05/new-plugins-submitted-ai.png)

If we were to group them by functionality and ordered by number of submissions, we’d have these categories:

💬 Chatbots / Virtual Agents

✍️ Content Generators

🛒 Ecommerce / WooCommerce

🔍 SEO

🖼️ Multimedia Generation (images, 3D, etc.)

📝 Forms / Inputs

✨ Summaries / Highlights

❓ FAQ / Q&A Generators

🌐 Translation / Multilingual

🏷️ Taxonomy Management (categories/tags)

📋 Titles and Metadata

We highly appreciate developers betting on WordPress to include Artificial Intelligence and improve integration and functionalities for users.

## The Impact of AI on Plugin Development

Artificial intelligence has become a key tool to speed up and improve plugin development in WordPress. From writing code to generating ideas, here are some standout ways AI is helping:

- **Code Assistance**: AI tools assist developers by providing contextual suggestions, code snippets, and guidance on the use of WordPress-specific functions, hooks and APIs.

- **Code Debugging and Review:** AI can analyze your code and suggest improvements for performance, security, or WordPress standards compliance. It can help understand Plugin Check Plugin warnings and offer specific solutions.

- **Auxiliary Content and Documentation:** Automatically generate parts of documentation, FAQs, changelogs, or tutorials for end users.


## Improvements to the Team’s Internal Scanner

We’ve upgraded our internal tool focusing on three pillars: better detection, more examples, and AI integration.

We revamped the tool that assists our manual reviews by catching more issues and checking more detection points, while customizing examples to make it easier for developers to find solutions.

Remember, the main security issues stem from lack of sanitization, escaping, and nonce usage.

Finally, we’ve added AI to detect duplicate or similar plugin names in the directory, making the team more productive.

## Free Tool for WordPress Developers

Since last year, we have the [Plugin Check Plugin tool](https://wordpress.org/plugins/plugin-check/), which lets you review your own plugin. Plugin Check Plugin is an official tool that automatically checks if your plugin meets WordPress.org directory requirements and best practices.

More info is available in the [detailed introductory post](https://make.wordpress.org/plugins/2024/09/17/introducing-plugin-check-pcp/).

Since September 2024, Plugin Check Plugin has been integrated for [automatic reviews directly on WordPress.org](https://make.wordpress.org/plugins/2024/10/01/plugin-check-and-2fa-now-mandatory-for-new-plugin-submissions/), improving review speed and reducing issues by 41% when approving a plugin.

## Team Effort: Less Average Waiting Time

Even though we’ve received twice as many new plugin submissions, we should applaud the team’s dedication to keeping the time for first reviews low.

A short waiting time for plugin review encourages developers to publish in the directory and offers many advantages:

- Faster publishing cycle: Less time between idea and public availability.

- Better developer experience: Less waiting to validate ideas reduces frustration, increases motivation, and strengthens the WordPress community.

- Incentive to innovate more: Our community becomes more competitive with an agile process, encouraging experimentation and initial version releases.


This year, we are also managing to keep the average waiting time for the first review at a minimum. We work hard every day to maintain this commitment and avoid long delays that could discourage new plugin development.

_This post was written by [@davidperez](https://profiles.wordpress.org/davidperez/) and reviewed by [@frantorres](https://profiles.wordpress.org/frantorres/) and [@rabmalin](https://profiles.wordpress.org/rabmalin/)_

I am happy to see that the WordPress ecosystem is growing 💪💪. I am proud to be a WordPress contributor. 🤩

Thanks [@davidperez](https://profiles.wordpress.org/davidperez/) for sharing this insight.

Excellent – great to see the AI growth. This will be helpful for everyone in the ecosystem.

That’s fantastic guys.

## Site resources

ssearchccompose new postrreplyeedittgo to topjgo to the next post or commentkgo to the previous post or commentotoggle comment visibilityesccancel edit post or comment

0

Clear All