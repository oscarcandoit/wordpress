---
url: https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url
scraped_at: 2025-10-20T03:22:14.621Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

@wordpress/url


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Package Reference](https://developer.wordpress.org/block-editor/reference-guides/packages/)@wordpress/url

Search

# @wordpress/url

## In this article

Table of Contents

- [Installation](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#installation)
- [Usage](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#usage)
  - [addQueryArgs](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#addqueryargs)
  - [buildQueryString](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#buildquerystring)
  - [cleanForSlug](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#cleanforslug)
  - [filterURLForDisplay](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#filterurlfordisplay)
  - [getAuthority](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getauthority)
  - [getFilename](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getfilename)
  - [getFragment](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getfragment)
  - [getPath](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getpath)
  - [getPathAndQueryString](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getpathandquerystring)
  - [getProtocol](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getprotocol)
  - [getQueryArg](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getqueryarg)
  - [getQueryArgs](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getqueryargs)
  - [getQueryString](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#getquerystring)
  - [hasQueryArg](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#hasqueryarg)
  - [isEmail](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#isemail)
  - [isPhoneNumber](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#isphonenumber)
  - [isURL](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#isurl)
  - [isValidAuthority](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#isvalidauthority)
  - [isValidFragment](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#isvalidfragment)
  - [isValidPath](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#isvalidpath)
  - [isValidProtocol](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#isvalidprotocol)
  - [isValidQueryString](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#isvalidquerystring)
  - [normalizePath](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#normalizepath)
  - [prependHTTP](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#prependhttp)
  - [prependHTTPS](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#prependhttps)
  - [removeQueryArgs](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#removequeryargs)
  - [safeDecodeURI](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#safedecodeuri)
  - [safeDecodeURIComponent](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#safedecodeuricomponent)
- [Contributing to this package](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#contributing-to-this-package)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/#wp--skip-link--target)

A collection of utilities to manipulate URLs.

## [Installation](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#installation)

Install the module

```bash
npm install @wordpress/url --save

```

_This package assumes that your code will run in an **ES2015+** environment. If you’re using an environment that has limited or no support for such language features and APIs, you should include [the polyfill shipped in `@wordpress/babel-preset-default`](https://github.com/WordPress/gutenberg/tree/HEAD/packages/babel-preset-default#polyfill) in your code._

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#usage)

### [addQueryArgs](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#addqueryargs)

Appends arguments as querystring to the provided URL. If the URL already includes query arguments, the arguments are merged with (and take precedent over) the existing set.

_Usage_

```js
const newURL = addQueryArgs( 'https://google.com', { q: 'test' } ); // https://google.com/?q=test

```

_Parameters_

- _url_ `string`: URL to which arguments should be appended. If omitted, only the resulting querystring is returned.
- _args_ `Record< string, unknown >`: Query arguments to apply to URL.

_Returns_

- `string`: URL with arguments applied.

### [buildQueryString](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#buildquerystring)

Generates URL-encoded query string using input query data.

It is intended to behave equivalent as PHP’s `http_build_query`, configured with encoding type PHP\_QUERY\_RFC3986 (spaces as `%20`).

_Usage_

```js
const queryString = buildQueryString( {
    simple: 'is ok',
    arrays: [ 'are', 'fine', 'too' ],
    objects: {
        evenNested: {
            ok: 'yes',
        },
    },
} );
// "simple=is%20ok&arrays%5B0%5D=are&arrays%5B1%5D=fine&arrays%5B2%5D=too&objects%5BevenNested%5D%5Bok%5D=yes"

```

_Parameters_

- _data_ `Record< string, unknown >`: Data to encode.

_Returns_

- `string`: Query string.

### [cleanForSlug](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#cleanforslug)

Performs some basic cleanup of a string for use as a post slug.

This replicates some of what `sanitize_title_with_dashes()` does in WordPress core, but is only designed to approximate what the slug will be.

Converts Latin-1 Supplement and Latin Extended-A letters to basic Latin letters. Removes combining diacritical marks. Converts whitespace, periods, and forward slashes to hyphens. Removes any remaining non-word characters except hyphens. Converts remaining string to lowercase. It does not account for octets, HTML entities, or other encoded characters.

_Parameters_

- _string_ `string`: Title or slug to be processed.

_Returns_

- `string`: Processed string.

### [filterURLForDisplay](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#filterurlfordisplay)

Returns a URL for display.

_Usage_

```js
const displayUrl = filterURLForDisplay(
    'https://www.wordpress.org/gutenberg/'
); // wordpress.org/gutenberg
const imageUrl = filterURLForDisplay(
    'https://www.wordpress.org/wp-content/uploads/img.png',
    20
); // …ent/uploads/img.png

```

_Parameters_

- _url_ `string`: Original URL.
- _maxLength_ `number | null`: URL length.

_Returns_

- `string`: Displayed URL.

### [getAuthority](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getauthority)

Returns the authority part of the URL.

_Usage_

```js
const authority1 = getAuthority( 'https://wordpress.org/help/' ); // 'wordpress.org'
const authority2 = getAuthority( 'https://localhost:8080/test/' ); // 'localhost:8080'

```

_Parameters_

- _url_ `string`: The full URL.

_Returns_

- `string | void`: The authority part of the URL.

### [getFilename](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getfilename)

Returns the filename part of the URL.

_Usage_

```js
const filename1 = getFilename( 'http://localhost:8080/this/is/a/test.jpg' ); // 'test.jpg'
const filename2 = getFilename( '/this/is/a/test.png' ); // 'test.png'

```

_Parameters_

- _url_ `string`: The full URL.

_Returns_

- `string | void`: The filename part of the URL.

### [getFragment](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getfragment)

Returns the fragment part of the URL.

_Usage_

```js
const fragment1 = getFragment(
    'http://localhost:8080/this/is/a/test?query=true#fragment'
); // '#fragment'
const fragment2 = getFragment(
    'https://wordpress.org#another-fragment?query=true'
); // '#another-fragment'

```

_Parameters_

- _url_ `string`: The full URL

_Returns_

- `string | void`: The fragment part of the URL.

### [getPath](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getpath)

Returns the path part of the URL.

_Usage_

```js
const path1 = getPath( 'http://localhost:8080/this/is/a/test?query=true' ); // 'this/is/a/test'
const path2 = getPath( 'https://wordpress.org/help/faq/' ); // 'help/faq'

```

_Parameters_

- _url_ `string`: The full URL.

_Returns_

- `string | void`: The path part of the URL.

### [getPathAndQueryString](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getpathandquerystring)

Returns the path part and query string part of the URL.

_Usage_

```js
const pathAndQueryString1 = getPathAndQueryString(
    'http://localhost:8080/this/is/a/test?query=true'
); // '/this/is/a/test?query=true'
const pathAndQueryString2 = getPathAndQueryString(
    'https://wordpress.org/help/faq/'
); // '/help/faq'

```

_Parameters_

- _url_ `string`: The full URL.

_Returns_

- `string`: The path part and query string part of the URL.

### [getProtocol](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getprotocol)

Returns the protocol part of the URL.

_Usage_

```js
const protocol1 = getProtocol( 'tel:012345678' ); // 'tel:'
const protocol2 = getProtocol( 'https://wordpress.org' ); // 'https:'

```

_Parameters_

- _url_ `string`: The full URL.

_Returns_

- `string | void`: The protocol part of the URL.

### [getQueryArg](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getqueryarg)

Returns a single query argument of the url

_Usage_

```js
const foo = getQueryArg( 'https://wordpress.org?foo=bar&bar=baz', 'foo' ); // bar

```

_Parameters_

- _url_ `string`: URL.
- _arg_ `string`: Query arg name.

_Returns_

- `QueryArgParsed | undefined`: Query arg value.

### [getQueryArgs](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getqueryargs)

Returns an object of query arguments of the given URL. If the given URL is invalid or has no querystring, an empty object is returned.

_Usage_

```js
const foo = getQueryArgs( 'https://wordpress.org?foo=bar&bar=baz' );
// { "foo": "bar", "bar": "baz" }

```

_Parameters_

- _url_ `string`: URL.

_Returns_

- `QueryArgs`: Query args object.

### [getQueryString](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#getquerystring)

Returns the query string part of the URL.

_Usage_

```js
const queryString = getQueryString(
    'http://localhost:8080/this/is/a/test?query=true#fragment'
); // 'query=true'

```

_Parameters_

- _url_ `string`: The full URL.

_Returns_

- `string | void`: The query string part of the URL.

### [hasQueryArg](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#hasqueryarg)

Determines whether the URL contains a given query arg.

_Usage_

```js
const hasBar = hasQueryArg( 'https://wordpress.org?foo=bar&bar=baz', 'bar' ); // true

```

_Parameters_

- _url_ `string`: URL.
- _arg_ `string`: Query arg name.

_Returns_

- `boolean`: Whether or not the URL contains the query arg.

### [isEmail](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#isemail)

Determines whether the given string looks like an email.

_Usage_

```js
const isEmail = isEmail( 'hello@wordpress.org' ); // true

```

_Parameters_

- _email_ `string`: The string to scrutinise.

_Returns_

- `boolean`: Whether or not it looks like an email.

### [isPhoneNumber](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#isphonenumber)

Determines whether the given string looks like a phone number.

_Usage_

```js
const isPhoneNumber = isPhoneNumber( '+1 (555) 123-4567' ); // true

```

_Parameters_

- _phoneNumber_ `string`: The string to scrutinize.

_Returns_

- `boolean`: Whether or not it looks like a phone number.

### [isURL](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#isurl)

Determines whether the given string looks like a URL.

_Related_

- [https://url.spec.whatwg.org/](https://url.spec.whatwg.org/)
- [https://url.spec.whatwg.org/#valid-url-string](https://url.spec.whatwg.org/#valid-url-string)

_Usage_

```js
const isURL = isURL( 'https://wordpress.org' ); // true

```

_Parameters_

- _url_ `string`: The string to scrutinise.

_Returns_

- `boolean`: Whether or not it looks like a URL.

### [isValidAuthority](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#isvalidauthority)

Checks for invalid characters within the provided authority.

_Usage_

```js
const isValid = isValidAuthority( 'wordpress.org' ); // true
const isNotValid = isValidAuthority( 'wordpress#org' ); // false

```

_Parameters_

- _authority_ `string`: A string containing the URL authority.

_Returns_

- `boolean`: True if the argument contains a valid authority.

### [isValidFragment](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#isvalidfragment)

Checks for invalid characters within the provided fragment.

_Usage_

```js
const isValid = isValidFragment( '#valid-fragment' ); // true
const isNotValid = isValidFragment( '#invalid-#fragment' ); // false

```

_Parameters_

- _fragment_ `string`: The url fragment.

_Returns_

- `boolean`: True if the argument contains a valid fragment.

### [isValidPath](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#isvalidpath)

Checks for invalid characters within the provided path.

_Usage_

```js
const isValid = isValidPath( 'test/path/' ); // true
const isNotValid = isValidPath( '/invalid?test/path/' ); // false

```

_Parameters_

- _path_ `string`: The URL path.

_Returns_

- `boolean`: True if the argument contains a valid path

### [isValidProtocol](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#isvalidprotocol)

Tests if a url protocol is valid.

_Usage_

```js
const isValid = isValidProtocol( 'https:' ); // true
const isNotValid = isValidProtocol( 'https :' ); // false

```

_Parameters_

- _protocol_ `string`: The url protocol.

_Returns_

- `boolean`: True if the argument is a valid protocol (e.g. http:, tel:).

### [isValidQueryString](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#isvalidquerystring)

Checks for invalid characters within the provided query string.

_Usage_

```js
const isValid = isValidQueryString( 'query=true&another=false' ); // true
const isNotValid = isValidQueryString( 'query=true?another=false' ); // false

```

_Parameters_

- _queryString_ `string`: The query string.

_Returns_

- `boolean`: True if the argument contains a valid query string.

### [normalizePath](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#normalizepath)

Given a path, returns a normalized path where equal query parameter values will be treated as identical, regardless of order they appear in the original text.

_Parameters_

- _path_ `string`: Original path.

_Returns_

- `string`: Normalized path.

### [prependHTTP](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#prependhttp)

Prepends “http://” to a url, if it looks like something that is meant to be a TLD.

_Usage_

```js
const actualURL = prependHTTP( 'wordpress.org' ); // http://wordpress.org

```

_Parameters_

- _url_ `string`: The URL to test.

_Returns_

- `string`: The updated URL.

### [prependHTTPS](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#prependhttps)

Prepends “https://” to a url, if it looks like something that is meant to be a TLD.

Note: this will not replace “http://” with “<https://”>.

_Usage_

```js
const actualURL = prependHTTPS( 'wordpress.org' ); // https://wordpress.org

```

_Parameters_

- _url_ `string`: The URL to test.

_Returns_

- `string`: The updated URL.

### [removeQueryArgs](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#removequeryargs)

Removes arguments from the query string of the url

_Usage_

```js
const newUrl = removeQueryArgs(
    'https://wordpress.org?foo=bar&bar=baz&baz=foobar',
    'foo',
    'bar'
); // https://wordpress.org?baz=foobar

```

_Parameters_

- _url_ `string`: URL.
- _args_ `string[]`: Query Args.

_Returns_

- `string`: Updated URL.

### [safeDecodeURI](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#safedecodeuri)

Safely decodes a URI with `decodeURI`. Returns the URI unmodified if `decodeURI` throws an error.

_Usage_

```js
const badUri = safeDecodeURI( '%z' ); // does not throw an Error, simply returns '%z'

```

_Parameters_

- _uri_ `string`: URI to decode.

_Returns_

- `string`: Decoded URI if possible.

### [safeDecodeURIComponent](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#safedecodeuricomponent)

Safely decodes a URI component with `decodeURIComponent`. Returns the URI component unmodified if `decodeURIComponent` throws an error.

_Parameters_

- _uriComponent_ `string`: URI component to decode.

_Returns_

- `string`: Decoded URI component if possible.

## [Contributing to this package](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-url/\#contributing-to-this-package)

This is an individual package that’s part of the Gutenberg project. The project is organized as a monorepo. It’s made up of multiple self-contained software packages, each with a specific purpose. The packages in this monorepo are published to [npm](https://www.npmjs.com/) and used by [WordPress](https://make.wordpress.org/core/) as well as other software projects.

To find out more about contributing to this package or Gutenberg as a whole, please read the project’s main [contributor guide](https://github.com/WordPress/gutenberg/tree/HEAD/CONTRIBUTING.md).

First published

March 9, 2021

Last updated

October 17, 2025

Edit article

[Improve it on GitHub: @wordpress/url](https://github.com/WordPress/gutenberg/edit/trunk/packages/url/README.md)

[Previous@wordpress/upload-mediaPrevious: @wordpress/upload-media](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-upload-media/)

[Next@wordpress/viewportNext: @wordpress/viewport](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-viewport/)

Notifications