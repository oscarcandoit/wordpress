---
url: https://developer.wordpress.org/coding-standards/styleguide
scraped_at: 2025-10-20T04:34:13.807Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/coding-standards/styleguide/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Markdown Style Guide


[Home](https://developer.wordpress.org/)[Coding Standards Handbook](https://developer.wordpress.org/coding-standards/)Markdown Style Guide

Search

# Markdown Style Guide

## In this article

Table of Contents

- [Headings](https://developer.wordpress.org/coding-standards/styleguide/#headings)
- [Emphasis](https://developer.wordpress.org/coding-standards/styleguide/#emphasis)
  - [Italics](https://developer.wordpress.org/coding-standards/styleguide/#italics)
  - [Bold](https://developer.wordpress.org/coding-standards/styleguide/#bold)
  - [Strikethrough](https://developer.wordpress.org/coding-standards/styleguide/#strikethrough)
- [Links](https://developer.wordpress.org/coding-standards/styleguide/#links)
- [Blockquotes](https://developer.wordpress.org/coding-standards/styleguide/#blockquotes)
- [Lists](https://developer.wordpress.org/coding-standards/styleguide/#lists)
  - [Unordered Lists](https://developer.wordpress.org/coding-standards/styleguide/#unordered-lists)
  - [Ordered Lists](https://developer.wordpress.org/coding-standards/styleguide/#ordered-lists)
- [Horizontal Rules](https://developer.wordpress.org/coding-standards/styleguide/#horizontal-rules)
- [Tables](https://developer.wordpress.org/coding-standards/styleguide/#tables)
- [Example Code](https://developer.wordpress.org/coding-standards/styleguide/#example-code)
  - [Inline Code](https://developer.wordpress.org/coding-standards/styleguide/#inline-code)
  - [Fenced Code Blocks](https://developer.wordpress.org/coding-standards/styleguide/#fenced-code-blocks)

[↑ Back to top](https://developer.wordpress.org/coding-standards/styleguide/#wp--skip-link--target)

## [Headings](https://developer.wordpress.org/coding-standards/styleguide/\#headings)

```md
# Heading h1
## Heading h2
### Heading h3
#### Heading h4
##### Heading h5
###### Heading h6

```

Note: h1 – h4 items will be automatically added to the Table of Contents.

## [Emphasis](https://developer.wordpress.org/coding-standards/styleguide/\#emphasis)

### [Italics](https://developer.wordpress.org/coding-standards/styleguide/\#italics)

Wrap text with a single `_` for _Italic_ text:

```md
This is _italic text_.

```

### [Bold](https://developer.wordpress.org/coding-standards/styleguide/\#bold)

Wrap text with double `**` for **Bold** text:

```md
This is **bold text**.

```

### [Strikethrough](https://developer.wordpress.org/coding-standards/styleguide/\#strikethrough)

Wrap text with double `~~` for ~~strikethrough~~ text:

```md
This is ~~strikethrough~~ text.

```

## [Links](https://developer.wordpress.org/coding-standards/styleguide/\#links)

Wrap the title in square brackets `[title]` immediately followed by the URL in `(https://example.com)`:

```md
[WordPress](https://wordpress.org/)

```

## [Blockquotes](https://developer.wordpress.org/coding-standards/styleguide/\#blockquotes)

Use `>` for blockquotes, double `>>` to further indent:

```md
> Blockquote
>> Indented Blockquote

```

## [Lists](https://developer.wordpress.org/coding-standards/styleguide/\#lists)

### [Unordered Lists](https://developer.wordpress.org/coding-standards/styleguide/\#unordered-lists)

Use `-` for unordered lists, and intent two spaces for list subitems:

```md
- List
  - List
- List
- List

```

### [Ordered Lists](https://developer.wordpress.org/coding-standards/styleguide/\#ordered-lists)

Use numbered items followed by a \`.:

```md
1. One
2. Two
3. Three

```

## [Horizontal Rules](https://developer.wordpress.org/coding-standards/styleguide/\#horizontal-rules)

Use `---` for a horizontal rules:

```md
---

```

## [Tables](https://developer.wordpress.org/coding-standards/styleguide/\#tables)

```md
| A     | B     |
| ----- | ----- |
| Alpha | Bravo |

```

## [Example Code](https://developer.wordpress.org/coding-standards/styleguide/\#example-code)

### [Inline Code](https://developer.wordpress.org/coding-standards/styleguide/\#inline-code)

Wrap inline code with single ``` `\`` ``` backticks:

````md
```
This is `inline code` wrapped with backticks
```

````

When documenting an example, use the markdown ``` `\`` ``` code block to demarcate the beginning and end of the code sample:

### [Fenced Code Blocks](https://developer.wordpress.org/coding-standards/styleguide/\#fenced-code-blocks)

#### [Javascript](https://developer.wordpress.org/coding-standards/styleguide/\#javascript)

````md
```javascript
var foo = function (bar) {
return bar++;
};

console.log(foo(5));
```

````

#### [JSON](https://developer.wordpress.org/coding-standards/styleguide/\#json)

````md
```json
{
"firstName": "John",
"lastName": "Smith",
"address": {
    "streetAddress": "21 2nd Street",
    "city": "New York",
    "state": "NY",
    "postalCode": "10021-3100"
},
"phoneNumbers": [\
    {\
      "type": "home",\
      "number": "212 555-1234"\
    },\
    {\
      "type": "office",\
      "number": "646 555-4567"\
    }\
],
"children": [],
"spouse": null
}
```

````

#### [CSS](https://developer.wordpress.org/coding-standards/styleguide/\#css)

````md
```css
foo {
padding: 5px;
margin-right: 3px;
}

.bar {
background-color: #f00;
}
```

````

#### [SCSS](https://developer.wordpress.org/coding-standards/styleguide/\#scss)

````md
```scss
foo {
padding: 5px;
margin-right: 3px;
}

.bar {
background-color: #f00;
}
```

````

#### [HTML](https://developer.wordpress.org/coding-standards/styleguide/\#html)

````md
```html
<span class="my-class">Example</span>
```

````

#### [PHP](https://developer.wordpress.org/coding-standards/styleguide/\#php)

````md
```php
$array = array(
    "foo" => "bar",
    "bar" => "foo",
);
```

````

#### [Markdown](https://developer.wordpress.org/coding-standards/styleguide/\#markdown)

````md
```md
This is _italic text_. This is **bold text**.
```

````

First published

December 18, 2019

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Markdown Style Guide](https://github.com/WordPress/wpcs-docs/edit/master/styleguide.md)

Changelog

[See list of changes: Markdown Style Guide](https://github.com/WordPress/wpcs-docs/commits/master/styleguide.md)

[PreviousChangelogPrevious: Changelog](https://developer.wordpress.org/coding-standards/changelog/)

Notifications