---
url: https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding
scraped_at: 2025-10-20T02:02:43.116Z
---

[Skip to content](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Linking and Embedding


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Using the REST API](https://developer.wordpress.org/rest-api/using-the-rest-api/)Linking and Embedding

Search

# Linking and Embedding

## In this article

Table of Contents

- [Links](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/#links)
  - [Example Response](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/#example-response)
- [Embedding](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/#embedding)
  - [Example Response](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/#example-response-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/#wp--skip-link--target)

The WP REST API incorporates hyperlinking throughout the API to allow discoverability and browsability, as well as embedding related resources together in one response. While the REST API does not completely conform to the entire [HAL standard](https://en.wikipedia.org/wiki/Hypertext_Application_Language), it implements the `._links` and `._embedded` properties from that standard as described below.

## [Links](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/\#links)

The `_links` property of the response object contains a map of links to other API resources, grouped by “relation.” The relation specifies how the linked resource relates to the primary resource.

Examples include:

– `author` – describing a relationship between a resource and its author

– `wp:term` – describing the relationship between a post and its tags or categories

The relation is either a

– [standardized relation](http://www.iana.org/assignments/link-relations/link-relations.xhtml#link-relations-1)

– a `URI relation` – like `https://api.w.org/term`

– or a `Compact URI relation` – like `wp:term`

Compact URI relations can be normalized to full URI relations to ensure full compatibility if required. This is similar to HTML `<link>` tags, or `<a rel="">` links.

The links are an object containing a `href` property with an absolute URL to the resource, as well as other optional properties. These include content types, disambiguation information, and data on actions that can be taken with the link.

For collection responses (those that return a list of objects rather than a top-level object), each item contains links, and the top-level response includes links via the `Link` header instead.

If your client library does not allow accessing headers, you can use the [`_envelope`](https://developer.wordpress.org/rest-api/global-parameters/#envelope) parameter to include the headers as body data instead.

### [Example Response](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/\#example-response)

A typical single post request ( `/wp/v2/posts/42`):

```js
{
  "id": 42,
  "_links": {
    "collection": [\
      {\
        "href": "https://example.com/wp-json/wp/v2/posts"\
      }\
    ],
    "author": [\
      {\
        "href": "https://example.com/wp-json/wp/v2/users/1",\
        "embeddable": true\
      }\
    ]
  }
}

```

## [Embedding](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/\#embedding)

Optionally, some linked resources may be included in the response to reduce the number of HTTP requests required. These resources are “embedded” into the main response.

Embedding is triggered by setting the [`_embed` query parameter](https://developer.wordpress.org/rest-api/using-the-rest-api/global-parameters/#_embed) on the request. This will then include embedded resources under the `_embedded` key adjacent to the `_links` key. The layout of this object mirrors the `_links` object, but includes the embedded resource in place of the link properties.

Only links with the `embeddable` flag set to `true` can be embedded, and `_embed` will cause all embeddable links to be embedded. Only relations containing embedded responses are included in `_embedded`, however relations with mixed embeddable and unembeddable links will contain dummy responses for the unembeddable links to ensure numeric indexes match those in `_links`.

When embedding a collection response, for instance `/wp/v2/posts?author=1`, the embedded collection will have the default pagination limits applied.

### [Example Response](https://developer.wordpress.org/rest-api/using-the-rest-api/linking-and-embedding/\#example-response-2)

```js
{
  "id": 42,
  "_links": {
    "collection": [\
      {\
        "href": "https://example.com/wp-json/wp/v2/posts"\
      }\
    ],
    "author": [\
      {\
        "href": "https://example.com/wp-json/wp/v2/users/1",\
        "embeddable": true\
      }\
    ]
  },
  "_embedded": {
    "author": {
      "id": 1,
      "name": "admin",
      "description": "Site administrator"
    }
  }
}

```

First published

December 6, 2016

Last updated

May 14, 2024

Edit article

[Improve it on GitHub: Linking and Embedding](https://github.com/WP-API/docs/edit/master/using-the-rest-api/linking-and-embedding.md)

Changelog

[See list of changes: Linking and Embedding](https://github.com/WP-API/docs/commits/master/using-the-rest-api/linking-and-embedding.md)

[PreviousGlobal ParametersPrevious: Global Parameters](https://developer.wordpress.org/rest-api/using-the-rest-api/global-parameters/)

[NextPaginationNext: Pagination](https://developer.wordpress.org/rest-api/using-the-rest-api/pagination/)

Notifications