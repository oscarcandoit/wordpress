---
url: https://developer.wordpress.org/apis/rewrite
scraped_at: 2025-10-20T04:07:27.343Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/rewrite/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Rewrite


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Rewrite

Search

# Rewrite

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/apis/rewrite/#description)
- [API Reference](https://developer.wordpress.org/apis/rewrite/#api-reference)

[↑ Back to top](https://developer.wordpress.org/apis/rewrite/#wp--skip-link--target)

## [Description](https://developer.wordpress.org/apis/rewrite/\#description)

WordPress allows theme and plugin developers to programmatically specify new, custom rewrite rules.

The following functions (which are mostly aliases for [WP\_Rewrite](https://developer.wordpress.org/reference/classes/wp_rewrite/) methods) can be used to achieve this.

Please note that these rules are usually called inside the `init` hook. Furthermore, permalinks will need to be refreshed (you can do this from WP-Admin under Settings -> Permalinks) before the rewrite changes will take effect. Requires one-time use of `flush_rules()` to take effect.

## [API Reference](https://developer.wordpress.org/apis/rewrite/\#api-reference)

#### [Articles](https://developer.wordpress.org/apis/rewrite/\#articles)

- Class: [`WP_Rewrite`](https://developer.wordpress.org/reference/classes/wp_rewrite/) – An overview of WordPress’s built-in URL rewrite class.

#### [Hooks](https://developer.wordpress.org/apis/rewrite/\#hooks)

- Filter: [`root_rewrite_rules`](https://developer.wordpress.org/reference/hooks/root_rewrite_rules/) – Filters the rewrite rules generated for the root of your weblog.
- Filter: [`post_rewrite_rules`](https://developer.wordpress.org/reference/hooks/post_rewrite_rules/) – Filters the rewrite rules generated for permalink URLs.
- Filter: [`page_rewrite_rules`](https://developer.wordpress.org/reference/hooks/page_rewrite_rules) – Filters the rewrite rules generated for your Pages.
- Filter: [`date_rewrite_rules`](https://developer.wordpress.org/reference/hooks/date_rewrite_rules) – Filters the rewrite rules generated for dated archive URLs.
- Filter: [`search_rewrite_rules`](https://developer.wordpress.org/reference/hooks/search_rewrite_rules) – Filters the rewrite rules generated for search URLs.
- Filter: [`comments_rewrite_rules`](https://developer.wordpress.org/reference/hooks/comments_rewrite_rules) – Filters the rewrite rules generated for the latest comment feed URLs.
- Filter: [`author_rewrite_rules`](https://developer.wordpress.org/reference/hooks/author_rewrite_rules/) – Filters the rewrite rules generated for author archive URLs.
- Filter: [`rewrite_rules_array`](https://developer.wordpress.org/reference/hooks/rewrite_rules_array/) – Filters _all_ the rewrite rules at once.
- Filter: [`{$permastructname}_rewrite_rules`](https://developer.wordpress.org/reference/hooks/permastructname_rewrite_rules/) – Can be used to create or modify rewrite rules for any custom permastructs, such as taxonomies or custom post types.
- Action: [`generate_rewrite_rules`](https://developer.wordpress.org/reference/hooks/generate_rewrite_rules/) – Runs **after** all the rules have been created.

#### [Functions](https://developer.wordpress.org/apis/rewrite/\#functions)

- [`add_rewrite_tag()`](https://developer.wordpress.org/reference/functions/add_rewrite_tag/) – Can be used to allow WordPress to recognize custom variables (particularly custom querystring variables).
- [`add_rewrite_rule()`](https://developer.wordpress.org/reference/functions/add_rewrite_rule/) – Allows you to specify new, custom rewrite rules.
- [`add_rewrite_endpoint()`](https://developer.wordpress.org/reference/functions/add_rewrite_endpoint/) – Add a new endpoint like /trackback/
- [`flush_rules()`](https://developer.wordpress.org/reference/classes/wp_rewrite/flush_rules/) – Regenerate the rewrite rules and save them to the database.
- [`flush_rewrite_rules()`](https://developer.wordpress.org/reference/functions/flush_rewrite_rules/) – Remove rewrite rules and then recreate rewrite rules.
- [`generate_rewrite_rules()`](https://developer.wordpress.org/reference/hooks/generate_rewrite_rules/) – Generates rewrite rules from a permalink structure
- [`add_permastruct()`](https://developer.wordpress.org/reference/functions/add_permastruct/) – Add a new permastruct
- [`add_feed()`](https://developer.wordpress.org/reference/functions/add_feed/)– Add a new feed type like `/atom1/`

First published

August 12, 2019

Last updated

November 21, 2022

[PreviousRESTPrevious: REST](https://developer.wordpress.org/apis/rest/)

[NextSecurityNext: Security](https://developer.wordpress.org/apis/security/)

Notifications