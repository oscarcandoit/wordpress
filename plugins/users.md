---
url: https://developer.wordpress.org/plugins/users
scraped_at: 2025-10-20T03:13:05.760Z
---

[Skip to content](https://developer.wordpress.org/plugins/users/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Users


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)Users

Search

# Users

## In this article

Table of Contents

- [Roles and Capabilities](https://developer.wordpress.org/plugins/users/#roles-and-capabilities)
- [The Principle of Least Privileges](https://developer.wordpress.org/plugins/users/#the-principle-of-least-privileges)

[↑ Back to top](https://developer.wordpress.org/plugins/users/#wp--skip-link--target)

A _User_ is an access account with corresponding capabilities within the WordPress installation. Each WordPress user has, at the bare minimum, a username, password and email address.

Once a user account is created, that user may log in using the WordPress Admin (or programmatically) to access WordPress functions and data. WordPress stores the Users in the `users` table.

## [Roles and Capabilities](https://developer.wordpress.org/plugins/users/\#roles-and-capabilities)

Users are assigned [roles](https://developer.wordpress.org/plugins/users/roles-and-capabilities/#roles), and each role has a set of [capabilities](https://developer.wordpress.org/plugins/users/roles-and-capabilities/#capabilities).

You can create new roles with their own set of capabilities. Custom capabilities can also be created and assigned to existing roles or new roles.

In WordPress, developers can take advantage of user roles to limit the set of actions an account can perform.

## [The Principle of Least Privileges](https://developer.wordpress.org/plugins/users/\#the-principle-of-least-privileges)

WordPress adheres to the principal of least privileges, the practice of giving a user _only_ the privileges that are essential for performing the desired work. You should follow this lead when possible by creating roles where appropriate and checking capabilities before performing sensitive tasks.

First published

September 24, 2014

Last updated

December 14, 2023

[PreviousWorking with Custom TaxonomiesPrevious: Working with Custom Taxonomies](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/)

[NextRoles and CapabilitiesNext: Roles and Capabilities](https://developer.wordpress.org/plugins/users/roles-and-capabilities/)

Notifications