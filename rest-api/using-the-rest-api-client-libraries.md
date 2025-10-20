---
url: https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries
scraped_at: 2025-10-20T02:01:58.502Z
---

[Skip to content](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Client Libraries


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Using the REST API](https://developer.wordpress.org/rest-api/using-the-rest-api/)Client Libraries

Search

# Client Libraries

## In this article

Table of Contents

- [PHP](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/#php)
- [JavaScript](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/#javascript)
- [Ruby](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/#ruby)
- [C# / .NET](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/#c-net)
- [Dart / Flutter](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/#dart-flutter)

[↑ Back to top](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/#wp--skip-link--target)

The API can be used from any application by sending basic HTTP requests; however, client libraries simplify the process of querying or creating specific resources. These libraries make it easy to connect an external application to the WordPress REST API using a variety of programming languages.

Aside from the Backbone.js client, these libraries are not part of WordPress core, and are not necessarily maintained or endorsed by the WordPress REST API team.

To perform authenticated requests from outside of the WordPress admin, themes, or plugins, a separate [authentication plugin](https://developer.wordpress.org/rest-api/authentication/#authentication-plugins) is required.

## [PHP](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/\#php)

[Requests](https://github.com/WordPress/Requests) for PHP is a general purpose HTTP request library. While not specifically designed for the WordPress REST API, it is a great tool for interacting with any HTTP API.

[WordPress-PHP-SDK](https://github.com/madeITBelgium/WordPress-PHP-SDK) is a PHP SDK for the WordPress REST API, which can be installed using [composer](https://getcomposer.org/).

[WordPress-SDK](https://github.com/storipress/wordpress-sdk) is a Laravel package for the WordPress REST API, which can be installed using [composer](https://getcomposer.org/).

## [JavaScript](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/\#javascript)

The [Backbone.js client](https://developer.wordpress.org/rest-api/backbone-javascript-client/) is built in to WordPress core and provides Backbone.js models & collections for working with REST API resources.

[node-wpapi](http://wp-api.org/node-wpapi) is an isomorphic JavaScript client library for querying or writing to the REST API using an intuitive chaining syntax. It can be used with Node.js or with client-side JavaScript applications.

[ember-wordpress](https://github.com/oskarrough/ember-wordpress) provides a connection between Ember Data and the REST API

## [Ruby](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/\#ruby)

[wp-api-client](https://github.com/duncanjbrown/wp-api-client): a read-only REST API client written in Ruby.

## [C\# / .NET](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/\#c-net)

[WordPressPCL](https://github.com/wp-net/WordPressPCL): a full REST API client written in C#.

## [Dart / Flutter](https://developer.wordpress.org/rest-api/using-the-rest-api/client-libraries/\#dart-flutter)

[wordpress\_client](https://pub.dev/packages/wordpress_client): A library exposing a fluent api to interact with the WordPress REST API.

First published

January 4, 2017

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Client Libraries](https://github.com/WP-API/docs/edit/master/using-the-rest-api/client-libraries.md)

Changelog

[See list of changes: Client Libraries](https://github.com/WP-API/docs/commits/master/using-the-rest-api/client-libraries.md)

[PreviousBackbone JavaScript ClientPrevious: Backbone JavaScript Client](https://developer.wordpress.org/rest-api/using-the-rest-api/backbone-javascript-client/)

[NextDiscoveryNext: Discovery](https://developer.wordpress.org/rest-api/using-the-rest-api/discovery/)

Notifications