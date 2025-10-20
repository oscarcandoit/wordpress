---
url: https://api.jquery.com/jQuery.cssNumber/
scraped_at: 2025-10-20T03:03:11.672Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.cssNumberReturns: [Object](http://api.jquery.com/Types/\#Object)version removed: [4.0](https://api.jquery.com/category/version/4.0/)

**Description:** An object containing all CSS properties that may be used without a unit. Prior to jQuery 4.0, the [`.css()`](https://api.jquery.com/css/) method uses this object to see if it may append `px` to unitless values.

- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/)jQuery.cssNumber


Note: This API has been removed in jQuery 4.0; please pass a string value with the desired units instead.

You can think about `jQuery.cssNumber` as a list of all CSS properties you might use without a unit. Prior to jQuery 4.0, it was used by [`.css()`](https://api.jquery.com/css/) to determine if it needs to add `px` to unitless values.

The keys of the `jQuery.cssNumber` object are camel-cased and the values are all set to `true`. If you want to prevent the [`.css()`](https://api.jquery.com/css/) method from automatically adding the `px` unit for a specific CSS property and that property is not yet a key of the `jQuery.cssNumber` object, you can add such an extra property:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

By default the object contains the following properties:

- `animationIterationCount` (added in 1.12.0/2.2.0)
- `aspectRatio` (added in 3.7.0)
- `borderImageSlice` (added in 3.7.0)
- `columnCount` (added in 1.9.0)
- `flexGrow` (added in 1.11.1/2.1.1)
- `flexShrink` (added in 1.11.1/2.1.1)
- `fontWeight` (added in 1.4.3)
- `gridArea` (added in 3.4.0)
- `gridColumn` (added in 3.4.0)
- `gridColumnEnd` (added in 3.4.0)
- `gridColumnStart` (added in 3.4.0)
- `gridRow` (added in 3.4.0)
- `gridRowEnd` (added in 3.4.0)
- `gridRowStart` (added in 3.4.0)
- `lineHeight` (added in 1.4.3)
- `opacity` (added in 1.4.3)
- `order` (added in 1.10.2/2.0.3)
- `orphans` (added in 1.6.0)
- `scale` (added in 3.7.0)
- `widows` (added in 1.6.0)
- `zIndex` (added in 1.4.3)
- `zoom` (added in 1.4.3)
- `fillOpacity` (SVG-related, added in 1.6.2)
- `floodOpacity` (SVG-related, added in 3.7.0)
- `stopOpacity` (SVG-related, added in 3.7.0)
- `strokeMiterlimit` (SVG-related, added in 3.7.0)
- `strokeOpacity` (SVG-related, added in 3.7.0)