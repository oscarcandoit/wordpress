---
url: https://make.wordpress.org/core/roadmap/multisite/
scraped_at: 2025-10-20T04:36:28.252Z
attempt: 1
---

[Skip to content](https://make.wordpress.org/core/roadmap/multisite/#primary)

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcore%2Froadmap%2Fmultisite%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[WordPress.org](https://wordpress.org/)

[Make WordPress Core](https://make.wordpress.org/core)

[**Menu**](https://make.wordpress.org/core/roadmap/multisite/#)

Show welcome box

## Welcome!

The WordPress core development team builds WordPress! Follow this site for general updates, status reports, and the occasional code debate. There’s lots of ways to contribute:

- **Found a bug?** [Create a ticket](https://wordpress.org/support/bb-login.php?redirect_to=https://core.trac.wordpress.org/newticket) in the bug tracker.
- **Want to contribute?** Get started quickly with tickets marked as [good first bugs](https://core.trac.wordpress.org/tickets/good-first-bugs) for new contributors or join a [bug scrub](https://make.wordpress.org/core/handbook/testing/bug-gardening/). There’s more on the [reports page](https://make.wordpress.org/core/reports/), like [patches needing testing](https://core.trac.wordpress.org/tickets/needs-testing), and on [feature projects page](https://make.wordpress.org/core/features/).
- **Other questions?** Here is a detailed [handbook for contributors](https://make.wordpress.org/core/handbook/), complete with tutorials.

## Communication

Core uses [Slack](https://make.wordpress.org/chat/) for real-time communication. Contributors live all over the world, so there are discussions happening at all hours of the day.

Core development meetings are every Wednesday at [15:00 UTC](https://time.is/1500_in_UTC) in the [**#core**](https://wordpress.slack.com/messages/core/) channel on [Slack](https://make.wordpress.org/chat/). Anyone can join and participate or listen in!

This roadmap contains plans for the multisite focus in the near future.

In addition to the common terms “users” and “roles”, the terms “sites”, “networks” and “global” are used in this roadmap. Here is what each of them means:

- **Sites:** A multisite setup has one or more sites that are connected to each other by being part of one setup and allowing several easy interactions and a common user base across. You manage a site through the regular site administration panel, with access to the respective areas determined by the role you have as a user.
- **Networks:** When setting up a multisite, you are essentially setting up a network. A network consists of one or more sites that belong together, one of which is its “main site”. You manage a network through the network administration panel, however only if you are set as a network administrator (also called “Super Admin”).
- **Global:** While it’s only possible to have one network given the UI that WordPress exposes, it also supports having multiple networks so that sites can be grouped together under distinct networks. When this is the case, a higher level in the hierarchy is required, for example to manage networks. This concept is rather abstract outside of multi-network, but global context means just that.

While this roadmap clearly states the main multisite objectives for the next several releases, it is by no means exclusive. Bugs and small enhancements can be addressed as needed.  Larger efforts and features should be discussed during weekly office hours and may be added to the roadmap. All tickets which are part of the roadmap can easily be looked up by using the [keyword ms-roadmap](https://core.trac.wordpress.org/query?status=accepted&status=assigned&status=new&status=reopened&status=reviewing&keywords=~ms-roadmap&col=id&col=summary&col=status&col=owner&col=type&col=priority&col=milestone&col=component&order=priority).

## REST API Support

### Users

The REST API has a `wp/v2/users` endpoint for managing users, however its implementation for multisite is incomplete. The users endpoint should be improved so that everything currently supported in the admin UI can be accomplished through the REST API.

Applications consuming the REST API should expect the same response from single site and multisite for objects that exist in both configurations.

A finished endpoint should provide the following:

- `GET wp/v2/users` – List users of the current site
- `GET wp/v2/users?global=true` – List all global users
- `GET wp/v2/users/<id>` – List a single user of the current site
- `GET wp/v2/users/<id>?global=true` – List a single global user
- `POST wp/v2/users` – Create a global user and add them to the current site
- `POST wp/v2/users?global=true` – Create a global user, do not add to a site
- `POST wp/v2/users?existing=true` – Add an existing user to the current site
- `POST/PUT/PATCH wp/v2/users/<id>` – Update site user data on current site
- `POST/PUT/PATCH wp/v2/users/<id>?global=true` – Update global user data
- `DELETE wp/v2/users/<id>` – Remove a single user from current site
- `DELETE wp/v2/users/<id>?global=true` – Delete a global user

In the examples above, a  new global parameter is introduced. When called without a global parameter, only user data associated with the current site (the site through which the REST API is accessed) can be changed. REST requests for users that are not associated with the current site should receive a 404 response if `global=true` is not included in the request. Only network administrators will have access to using the global parameter initially.

Related ticket: [#39544](https://core.trac.wordpress.org/ticket/39544)

### Sites

A new sites endpoint should exist primarily to manage site data in the wp\_blogs table. It should manage this data in a global context, while the site’s settings should be managed through its own `wp/v2/settings` endpoint.

A finished endpoint should provide the following:

- `GET wp/v2/sites` – List all sites
- `GET wp/v2/sites/<id>` – List a single site
- `POST wp/v2/sites` – Create a site
- `POST/PUT/PATCH wp/v2/sites/<id>` – Update a site
- `DELETE wp/v2/sites/<id>` – Delete a site

As there is no current method to discover all public sites on a network, any listing of **all** sites should require the `manage_sites` capability by default, with a new filter provided which allows changing that behavior.

It should however be possible to generate a list of a user’s sites separately from a listing based on the `manage_sites` capability. This will require `get_blogs_of_user()` or something similar and may need an additional parameter like `?user_id=<id>` to identify context.

Related ticket: [#40365](https://core.trac.wordpress.org/ticket/40365)

### Networks

While managing networks has never been part of core’s UI, there should be a basic networks endpoint to manage network data in the `wp_site` table. Since there are several plugins and custom solutions around for managing networks, this endpoint must not be opinionated. It should be a simple interface to the database table, to provide a common foundation for plugins implementing multi-network.

A finished endpoint should provide the following:

- `GET wp/v2/networks` – List all networks
- `GET wp/v2/networks/<id>` – List a single network
- `POST wp/v2/networks` – Create a network
- `POST/PUT/PATCH wp/v2/networks/<id>` – Update a network
- `DELETE wp/v2/networks/<id>` – Delete a network

Related ticket: [#41459](https://core.trac.wordpress.org/ticket/41459)

## Internal APIs

### Sites

The internal sites API should be revamped to support the wp/v2/sites endpoint work and other site-related development. Better equivalents should be introduced for the inconsistent functions that create, update, and delete site datain the wp\_blogs table:

- `insert_blog()` should be replaced with `wp_insert_site()`
- `update_blog_details()` should be replaced with `wp_update_site()`
- a new `wp_delete_site()` should be responsible for deleting a `wp_blogs` row

This completes a full CRUD API, together with the existing `get_site()` and `get_sites()`.

Related ticket: [#40364](https://core.trac.wordpress.org/ticket/40364)

In addition to a basic CRUD API, a new `get_site_by()` function should be introduced as an improved version of `get_blog_details()`.

Related tickets: [#40180](https://core.trac.wordpress.org/ticket/40180), [#40228](https://core.trac.wordpress.org/ticket/40228)

The installation and uninstallation of a site’s database tables, including initial data, should happen in dedicated functions as well:

- `install_blog()` should be replaced with `wp_install_site()` which will call `wp_install_defaults()` to handle the entire site installation process
- A new `wp_uninstall_site()` should handle dropping the site database tables, removing media etc., all of which is currently part of `wpmu_delete_blog()`

Related ticket: [#41333](https://core.trac.wordpress.org/ticket/41333)

`wp_insert_site()`, `wp_update_site()` and `wp_delete_site()` will all include a hook of the same name. The `wp_install_site()` function will be hooked into `wp_insert_site` by default, and `wp_uninstall_site()` will be hooked into `wp_delete_site`.

Note that the future of the old functions will be discussed at a later point. It will need to be determined individually whether they should remain as is, wrap new functionality and/or be deprecated. The only thing that is for sure is that they need to remain backward-compatible, as always.

### Site Metadata

In addition to the wp\_blogs table, there is a regular need for site-related data that should be part of the global context. For example, to extend the new `wp/v2/sites` endpoint, list the additional data in a performant way or query by it. Therefore a new database table `wp_blogmeta` should be introduced (that name is required for legacy reasons), alongside with the common metadata CRUD functions:

- `get_site_meta()`
- `add_site_meta()`
- `update_site_meta()`
- `delete_site_meta()`

This meta query functionality should also be added to `WP_Site_Query`.

The addition of the new database table must be carefully prepared, since core has never before introduced a new global table.

Related tickets: [#37923](https://core.trac.wordpress.org/ticket/37923), [#40229](https://core.trac.wordpress.org/ticket/40229)

### Networks

Similar to the planned `wp/v2/networks` endpoint, a basic unopinionated CRUD API for managing networks in the `wp_site` table should be available. It should follow a similar approach to the CRUD API for sites, with the following new functions:

- `wp_insert_network()` for adding a new table row
- `wp_update_network()` for updating the table row
- `wp_delete_network()` for deleting the table row

This completes a full CRUD API, together with the existing `get_network()` and `get_networks()`.

Related ticket: [#29411](https://core.trac.wordpress.org/ticket/29411)

### Network Metadata

Network settings are currently stored in a `wp_sitemeta` table, which is actually a table for metadata. While there is a dedicated API for network options, the metadata API is more performant and generally more regularly improved as it affects so many areas of WordPress. Therefore the `*_network_option()` functions should be changed to use the metadata API internally.

Related ticket: [#37181](https://core.trac.wordpress.org/ticket/37181)

### File Organization

Two new files `wp-includes/ms-site.php` and `wp-includes/ms-network.php` will be added, and all functions related to the current version of the site and network CRUD APIs, including metadata functions, will be moved to these files respectively. This will provide a better overview and make it apparent where a certain multisite function is located.

The second change in the file organization is that the metadata API files `wp-includes/meta.php`, `wp-includes/class-wp-meta-query.php` and `wp-includes/class-wp-metadata-lazyloader.php` will be loaded earlier in the bootstrapping process. This is necessary in order for the site and network meta APIs to work when accessed early, for example in a custom `sunrise.php` script.

Related tickets: [#40647](https://core.trac.wordpress.org/ticket/40647), [#40948](https://core.trac.wordpress.org/ticket/40948)

## Administration

### Users

There are significant improvements to be made in how users are managed on networks and sites. User administration in the dashboard should be updated to use REST API endpoints once they are feature complete.

This portion of the roadmap should be developed to include design and user testing once endpoints are ready.

### Sites

Site administration in the dashboard should be updated to use REST API endpoints once they are feature complete.

This portion of the roadmap should be developed to include design and user testing once endpoints are ready.

### Networks

Multisite provides a data structure for networks that is open to interpretation. Because of this, networks can be (and are) managed in widely different ways. Rather than make decisions on how networks should be managed, WordPress should embrace the current state and leave the management of networks to plugins and other custom code.

As mentioned before, WordPress core should provide methods for managing the data in the `wp_site` and `wp_sitemeta` tables so that code built on top of WordPress has a reliable and testable base.

Efforts for a “default” multi-network UI however should be focused on the [WP Multi Network](https://wordpress.org/plugins/wp-multi-network/) plugin, which has closely followed developments of multisite over the years and is the de facto standard for administrators looking to start with multiple networks.

## Bootstrapping and testing Multisite

The stability and testability of the multisite bootstrap process should continue to improve.

Core unit tests currently run with `SUBDOMAIN_INSTALL` set to false by default. Full support for subdomains should be reflected in testing and CI configurations.

Related tickets: [#42093](https://core.trac.wordpress.org/ticket/42093), [#40646](https://core.trac.wordpress.org/ticket/40646).

## Global Context Improvements

While global context enhancements have a lower priority than other tasks on the roadmap, it is important to think about related requirements and keep them in mind for future changes.

While core will likely never include a dedicated user interface for global data similarly like it will not include a UI for managing multiple networks, a storage for globally stored values would be a valuable enhancement. Currently, only users are truly stored globally, but there are other pieces of data that would benefit from a global storage, such as the network settings `user_count`, `global_terms_enabled` and `ms_files_rewriting` or the transients for available core, plugin and theme updates. All of these are currently stored on the network level although they are supposed to have the same value everywhere. Current ideas to fix that revolve around either having a new table such as `global_options`, or alternatively use the network options table `sitemeta` with an ID of 0 to address global scope.

Another issue related to the mixture between global and network scope is that users are global, but are currently exposed on the network level through the UI. This is once again fine in an environment that consists of only a single network, but in a multi-network there is currently no way to determine users of a particular network as there is no association between a user and their network. Fixing this would either involve a complex data migration path or it could alternatively be something that would only be enabled for new setups (which would then be something else that could be stored as a global setting).

Last but not least, there are also no global roles. Currently a “super admin” is a user that usually interpreted as a network administrator, but there is no level above that. Furthermore there is complexity in terminology in that term as it is often unclear whether the super admin user should have all capabilities or whether they should only have all capabilities in their specific network. For example, super admins are stored in a network setting, but they can be overridden by a global variable that would essentially make them global administrators. As super admins are only stored in a setting, a dedicated network level role system inspired by the existing site level role system could be the right direction to resolve this problem in the future, requiring a migration of existing super admins to a “Network Administrator” role. A simpler, but potentially not as efficient alternative could be a global setting similar to the super admins network setting.

## Site resources

ssearchccompose new postrreplyeedittgo to topjgo to the next post or commentkgo to the previous post or commentotoggle comment visibilityesccancel edit post or comment

0

Clear All