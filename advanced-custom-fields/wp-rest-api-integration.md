---
url: https://www.advancedcustomfields.com/resources/wp-rest-api-integration
scraped_at: 2025-10-20T02:32:51.418Z
---

# WP REST API Integration

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#overview)

## Overview

Link copied

Since [version 5.11](https://www.advancedcustomfields.com/blog/acf-5-11-release-rest-api/), ACF has included support for viewing and managing custom fields via the [WordPress REST API](https://developer.wordpress.org/rest-api/). This allows developers to access and edit their custom field data using default [WP REST API endpoints](https://developer.wordpress.org/rest-api/key-concepts/#routes-endpoints), or build [custom themes using React, Vue](https://deliciousbrains.com/creating-a-wordpress-theme-using-the-rest-api-and-vue-js/), or any other JavaScript library.

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#endpoints)

## Endpoints

Link copied

Any custom field groups added to WordPress data like posts (including custom post types), users, and categories (including [custom taxonomies](https://www.advancedcustomfields.com/blog/custom-taxonomy-wordpress/)) will be available in their respective WP REST API endpoints, namely:

- /{post-type}

  - posts, pages, custom-post-types, etc.
- /{post-type}/{post\_id}
- /{post-type}/{post\_id}/revisions
- /{post-type}/{post\_id}/revisions/{revision\_id}
- /{post-type}/{post\_id}/autosaves
- /{post-type}/{post\_id}/autosaves/{autosave\_id}
- /users
- /users/{user\_id}
- /users/me
- /categories
- /categories/{category\_id}
- /{custom-taxonomy}/{term\_id}

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#enabling-the-rest-api-for-your-acf-fields)

## Enabling the REST API for Your ACF Fields

Link copied

By default, field groups are not visible in the WP REST API. You must opt-in if you want them to show in the WP REST API.

You can enable REST API visibility for a specific field group in its [Settings](https://www.advancedcustomfields.com/resources/creating-a-field-group/#settings) area. Click the **Group Settings** tab, and then click **Show in REST API**.

![The Group Settings tab for an ACF field group, with “Show in REST API” toggled on. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/11/ACF-Show-in-REST-API.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#using-the-rest-api-with-custom-post-types-and-taxonomies)

## Using the REST API With Custom Post Types and Taxonomies

Link copied

By default, custom post types and taxonomies created in ACF _are_ visible in the WP REST API, with a default namespace of `wp/v2` and default controller class of `WP_REST_Posts_Controller` for post types, and `WP_REST_Terms_Controller` for taxonomies.

To change the default REST API visibility or settings for custom post types, navigate to **ACF > Post Types**, and select or [register a custom post type](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/). Toggle on **Advanced Configuration** to open “Advanced Settings”. Click the **REST API** tab to access the settings, including visibility, namespace, and controller class. This tab also allows you to create a base URL for the post type REST API URLs.

![The ACF post type editor showing the default settings for showing a post type in the REST API.](https://www.advancedcustomfields.com/wp-content/uploads/2023/11/ACF-WP-REST-API-Integration-Custom-Post-Types-in-REST-API.png)

A similar process can be followed for custom taxonomies.

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#request-methods)

## Request Methods

Link copied

The following three request methods can be used in conjunction with ACF data:

1. GET requests allow you to view ACF data.
2. OPTIONS requests allow you to view the schema for the ACF data.
3. POST requests allow you to update any ACF fields, and require you to [authenticate](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#authentication) to perform the request.

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#get-request)

### GET request

Link copied

A GET request will show the ACF data in the REST response.

In the following example, we’ve configured a custom post type `book`, and an [ACF field group](https://www.advancedcustomfields.com/resources/creating-a-field-group/) for all books, with Author (Text), Author Bio (WYSIWYG), and Author Image (Image) fields. We’ll add data to each book for these custom fields.

![Creating an ACF field group, with the fields outlined in the text above. The “Location Rules” in “Settings” have been set to show the field group if the post type is equal to “Book.”](https://www.advancedcustomfields.com/wp-content/uploads/2024/01/ACF-WP-REST-API-Author-Info-and-Book-Example.png)

Performing a GET request to `https://hellfish.media/wp-json/wp/v2/book/{ID}`, where `{ID}` is the ID of the given book, shows the custom field data in the `acf` JSON object, just below the `template` data.

```json php
{
  "id": 3944,
  "date": "2021-11-15T10:11:38",
  "date_gmt": "2021-11-15T10:11:38",
  "guid": {
    "rendered": "https://hellfish.media/?post_type=book&p=3944"
  },
  "modified": "2021-11-15T10:11:52",
  "modified_gmt": "2021-11-15T10:11:52",
  "slug": "tales-of-the-flying-hellfish",
  "status": "publish",
  "type": "book",
  "link": "https://hellfish.media/book/tales-of-the-flying-hellfish/",
  "title": {
    "rendered": "Tales of the Flying Hellfish"
  },
  "content": {
    "rendered": "<p>The <b>Flying Hellfish</b> (also referred to as just &#8220;<b>the Hellfish</b>&#8220;) was the military unit <a class=\"mw-redirect\" title=\"Abraham Simpson\" href=\"https://simpsons.fandom.com/wiki/Abraham_Simpson\">Abraham Simpson</a>, <a title=\"Charles Montgomery Burns\" href=\"https://simpsons.fandom.com/wiki/Charles_Montgomery_Burns\">Charles Montgomery Burns</a>, and several other <a title=\"Springfield\" href=\"https://simpsons.fandom.com/wiki/Springfield\">Springfieldians</a> served in during <a title=\"World War II\" href=\"https://simpsons.fandom.com/wiki/World_War_II\">World War II</a>.</p>\n<p>Presumably, the Flying Hellfish was first dispatched to Normandy for the <a class=\"extiw\" title=\"wikipedia:Invasion of Normandy\" href=\"http://en.wikipedia.org/wiki/Invasion_of_Normandy\">Invasion of Normandy</a>.</p>\n<p>Burns was always the unit&#8217;s troublemaker. The Hellfish got stuck with Burns because he obstructed a probe from J. Edgar Hoover, thus resulting in his demotion. He faked his own death several times and even ruined Simpson&#8217;s chance to assassinate <a title=\"Adolf Hitler\" href=\"https://simpsons.fandom.com/wiki/Adolf_Hitler\">Adolf Hitler</a>.</p>\n<p>At one point, near the end of the war, the unit stormed a German castle. While searching through it, Private Burns found a collection of stolen paintings. While discussing what they should do with them, Burns mentions the idea of <a class=\"extiw\" title=\"wikipedia:Tontine\" href=\"http://en.wikipedia.org/wiki/Tontine\">tontine</a>, where the members must enter into a contract of when the last surviving member inherits the paintings if the others pass away. The unit agrees for their own personal reasons (Gumble wanting to buy his way into high society, Abe not wanting to end up &#8220;in one of them old folk&#8217;s homes&#8221;). Everyone signs and shakes on this prospect.</p>\n<p>Ox was the first member to die because of a <a class=\"extiw\" title=\"wikipedia:hernia\" href=\"http://en.wikipedia.org/wiki/hernia\">hernia</a> he got while taking the crate out of the castle. Five more were killed in a parade float accident in 1979. After Asa Phelps died, only Burns and Abe remained. Later, Simpson gave Burns a dishonorable discharge from the Hellfish for trying to kill him and his grandson <a title=\"Bart Simpson\" href=\"https://simpsons.fandom.com/wiki/Bart_Simpson\">Bart</a>, expelling him from the tontine and declaring himself the sole possessor of the paintings in default, much to Burns&#8217; dismay. Unfortunately for Grampa and Bart, their victory was cut short when the U.S. State Department arrive and took the paintings, as they have been searching for them for 50 years to avoid any international incidents with the German government. The State Department then returns the paintings to their rightful owner&#8217;s descendant, <a title=\"Baron von Herzenberger\" href=\"https://simpsons.fandom.com/wiki/Baron_von_Herzenberger\">Baron von Herzenberger</a>.</p>\n<p>&nbsp;</p>\n",
    "protected": false
  },
  "template": "",
  "acf": {
    "author": "Abraham Simpson",
    "author_bio": "<b>Abraham Jebediah \"Abe\" Simpson II</b>, commonly known as <b>Grampa Simpson</b> or simply <b>Grampa</b>, (born August 26, 1920) is a major character in <i><a title=\"The Simpsons\" href=\"https://simpsons.fandom.com/wiki/The_Simpsons\">The Simpsons</a></i>. He is the oldest patriarch of the <a title=\"Simpson family\" href=\"https://simpsons.fandom.com/wiki/Simpson_family\">Simpson family</a>, father of <a title=\"Homer Simpson\" href=\"https://simpsons.fandom.com/wiki/Homer_Simpson\">Homer Simpson</a>, and paternal grandfather of <a title=\"Bart Simpson\" href=\"https://simpsons.fandom.com/wiki/Bart_Simpson\">Bart</a>, <a title=\"Lisa Simpson\" href=\"https://simpsons.fandom.com/wiki/Lisa_Simpson\">Lisa</a> and <a title=\"Maggie Simpson\" href=\"https://simpsons.fandom.com/wiki/Maggie_Simpson\">Maggie Simpson</a>.",
    "author_image": 3949
  },
  "_links": {
    "self": [\
      {\
        "href": "https://hellfish.media/wp-json/wp/v2/book/3944"\
      }\
    ],
    "collection": [\
      {\
        "href": "https://hellfish.media/wp-json/wp/v2/book"\
      }\
    ],
    "about": [\
      {\
        "href": "https://hellfish.media/wp-json/wp/v2/types/book"\
      }\
    ],
    "wp:attachment": [\
      {\
        "href": "https://hellfish.media/wp-json/wp/v2/media?parent=3944"\
      }\
    ],
    "curies": [\
      {\
        "name": "wp",\
        "href": "https://api.w.org/{rel}",\
        "templated": true\
      }\
    ]
  }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#options-request)

### OPTIONS request

Link copied

Performing an OPTIONS request to a WordPress REST API endpoint allows you to see the [schema](https://developer.wordpress.org/rest-api/extending-the-rest-api/schema/) for that data object, i.e., the available fields and their properties. For ACF fields, it allows you to see details for the field. For example, the basic Text field can have a “Max Length” character limit, which will show up in the schema for that field. Please see [REST API Field Types](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#rest-api-field-types) for more details.

In our example post above, making an OPTIONS request will return the schema for the book, including data about the ACF fields we’ve set up.

```json php
{
  "acf": {
    "description": "ACF field data",
    "type": "object",
    "properties": {
      "author": {
        "type": [\
          "string",\
          "null"\
        ],
        "required": false
      },
      "author_bio": {
        "type": [\
          "string",\
          "null"\
        ],
        "required": false
      },
      "author_image": {
        "type": [\
          "integer",\
          "null"\
        ],
        "required": false
      }
    },
    "required": false
  }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#post-request)

### POST Request

Link copied

Performing a POST request will allow you to change data about the book. In our case, we can update the `author`, `author_bio`, and `author_image` ACF fields. Because POST requests allow you to change data, you will need to authenticate your request, using one of the [available authentication methods](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#authentication). To update your ACF field groups, you need to pass the data as a JSON encoded `acf` object, using the same structure as it appears in the GET request. In our example above, to update the `author` data, we would pass the following data:

```json php
{
  "acf": {
    "author": "Abraham (Abe) Simpson"
  }
}
```

Below is an example of making a POST request via JavaScript, using the WordPress [apiFetch](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-api-fetch/) utility:

```javascript php
import apiFetch from '@wordpress/api-fetch';

// POST
apiFetch( {
  path: '/wp/v2/book/{ID}',
  method: 'POST',
  data: {
    "acf": {
      "author": "Abraham (Abe) Simpson",
    }
  },
} ).then( ( res ) => {
  console.log( res );
} );
```

This will result in the `acf` object on the book being updated.

Passing `null` to your ACF fields deletes the content of the field:

```javascript php
import apiFetch from '@wordpress/api-fetch';

// POST
apiFetch( {
  path: '/wp/v2/book/{ID}',
  method: 'POST',
  data: {
    "acf": {
      "author_bio": null
    }
  },
} ).then( ( res ) => {
  console.log( res );
} );
```

This will result in the following `acf` object on the book:

```json php
{
  "acf": {
    "author": "Abraham (Abe) Simpson",
    "author_bio": "",
    "author_image": 3949
  }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#authentication)

## Authentication

Link copied

Since ACF uses core WP REST API endpoints, it uses core [authentication methods](https://developer.wordpress.org/rest-api/using-the-rest-api/authentication/) (cookies and nonces) by default. This means if you’re building something in the WordPress dashboard, the code will be run in an already logged-in session, and no specific authentication is needed.

Should you wish to build something using the REST API endpoints outside a logged-in session (for example a JavaScript application powered by the REST API), you will need to authenticate any POST requests. There are a number of ways to handle this authentication, including [Application Passwords](https://make.wordpress.org/core/2020/11/05/application-passwords-integration-guide/) (available in WordPress core) and the [JSON Web Tokens](https://wordpress.org/plugins/jwt-authentication-for-wp-rest-api/) plugin.

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#rest-api-field-types)

## REST API Field Types

Link copied

This table lists all ACF field types supported in the WP REST API.

| Field Type | Types | Notes |
| --- | --- | --- |
| Text | string, null |  |
| Text Area | string, null |  |
| Number | number, null | A string representation of a number is OK. e.g.; ‘123’. |
| Range | number, null | A string representation of a number is OK. e.g.; ‘123’. |
| Email | string (email), null | If value isn’t correct email format, request will fail with 400 bad request. |
| URL | string (uri), null | If string doesn’t have a protocol, the API will prefix http://. |
| Password | string, null |  |
| Image | integer, null | Expects attachment ID. |
| File | integer, null | Expects attachment ID. |
| Wysiwyg Editor | string, null |  |
| oEmbed | string (uri), null | If string doesn’t have a protocol, the API will prefix http://. |
| Gallery | number\[\], null | Array of attachment IDs. |
| Select | string, array, null | Will support either array or single string. Array to select multiple values. |
| Checkbox | string, array, null | Will support either array or single string. |
| Radio Button | string, null |  |
| Button Group | string, null |  |
| True/False | boolean, null | 0 and 1 can also be sent through as a string. |
| Link | object, null | Object accepts title, url, & target properties. |
| Post Object | int, array, null | Will support either array or single string. Array to select multiple values. |
| Page Link | string, int, array, null | Will support either array or single string. Array to select multiple values. |
| Relationship | int, array, null | Will support either array or single string. Array or CSV to select multiple values. |
| Taxonomy | string, array, null | Will support either array or single string. Array to select multiple values. |
| User | string, array, null | Will support either array or single string. Array or CSV to select multiple values. |
| Google Map | object, null | Can be as simple as lat, lng properties. Supports: address, lat, lng, zoom, place\_id, name, street\_number, street\_name, street\_name\_short, city, state, state\_short, post\_code, country, country\_short. |
| Date Picker | string, null | A Ymd formatted date string. |
| Date Time Picker | string, null | A Y-m-d H:i:s formatted date time string. |
| Time Picker | string, null | A H:i:s formatted time string. |
| Color Picker | string, null | Either a 6-char hex code, an RGB or an RGBA string. |
| Message |  | Not currently supported in the REST API. |
| Accordion |  | Not currently supported in the REST API. |
| Tab |  | Not currently supported in the REST API. |
| Group | object,null | An object containing the subfield names and values. |
| Repeater | array, null | An array of objects, each representing a row of values mapped to sub field names. |
| Flexible Content | array, null | An array of objects, each representing a layout of values mapped to sub field names. acf\_fc\_layout is a required property for each object and must match the name of a layout configured on the flexible content field being updated. |
| Clone | object, null | Will only appear in REST requests if the Clone field is set to Group mode. When set to Group mode, this property will accept an object containing the subfield names and values. If it’s set to Seamless mode instead, the fields being cloned will show up in its place. If the Clone field is marked as required, all subfields will also be required. |

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#developer-notes)

## Developer Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#disabling-the-acf-rest-api-system)

### Disabling the ACF REST API system

Link copied

It is possible to completely disable WP REST API support, by returning `false` to the `acf/settings/rest_api_enabled` filter. Doing so overrides any “Show in REST API” settings for your field groups, and completely disable WP REST API support for ACF:

```php php
add_filter( 'acf/settings/rest_api_enabled', '__return_false' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#extending-the-rest-api-system)

## Extending the REST API System

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#scoping-visible-fields-using-the-fields-query-parameter)

### Scoping visible fields using the \_fields query parameter

Link copied

The WP REST API `?_fields` [query parameter](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/(https://developer.wordpress.org/rest-api/using-the-rest-api/global-parameters/#_fields)) can be used to query just the `acf` object, or specific fields within it.

```php
// Return the acf object and all available fields:

/wp-json/wp/v2/book/{ID}?_fields=acf

// Return only a specific field from the acf object:

/wp-json/wp/v2/book/{ID}?_fields=acf.author,acf.author_bio

// Return a specific sub-field from a specific group field from the acf object:

/wp-json/wp/v2/book/{ID}?_fields=acf.author_meta.profile_url
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#controlling-output-format)

### Controlling the output format

Link copied

Using the `acf_format` parameter in your WP REST API request can be used to modify the output of a request.

The default value for this parameter is `light`, and it passes the field values to the `format_value_for_rest()` method on the specific field type object before rendering the data in the response. This applies very lightweight formatting and keeps the field output raw and in line with the schema. The example responses earlier in this document show the output of the `light` format.

Passing `standard` to the parameter will ensure that all fields will be formatted using the global `acf_format_value()` ACF function. Below is an example of passing `standard` to the parameter for our earlier example. As you can see, the `author_image` field now includes more information about the image:

```php
/wp-json/wp/v2/book/{ID}?_fields=acf&acf_format=standard
```

```json php
{
  "acf": {
    "author": "Abraham Simpson",
    "author_bio": "<p><b>Abraham Jebediah &#8220;Abe&#8221; Simpson II</b>, commonly known as <b>Grampa Simpson</b> or simply <b>Grampa</b>, (born August 26, 1920) is a major character in <i><a title=\"The Simpsons\" href=\"https://simpsons.fandom.com/wiki/The_Simpsons\">The Simpsons</a></i>. He is the oldest patriarch of the <a title=\"Simpson family\" href=\"https://simpsons.fandom.com/wiki/Simpson_family\">Simpson family</a>, father of <a title=\"Homer Simpson\" href=\"https://simpsons.fandom.com/wiki/Homer_Simpson\">Homer Simpson</a>, and paternal grandfather of <a title=\"Bart Simpson\" href=\"https://simpsons.fandom.com/wiki/Bart_Simpson\">Bart</a>, <a title=\"Lisa Simpson\" href=\"https://simpsons.fandom.com/wiki/Lisa_Simpson\">Lisa</a> and <a title=\"Maggie Simpson\" href=\"https://simpsons.fandom.com/wiki/Maggie_Simpson\">Maggie Simpson</a>.</p>\n",
    "author_image": {
      "ID": 3949,
      "id": 3949,
      "title": "Abraham_Simpson",
      "filename": "Abraham_Simpson.webp",
      "filesize": 28342,
      "url": "https://hellfish.media/wp-content/uploads/2021/11/Abraham_Simpson.webp",
      "link": "https://hellfish.media/book/tales-of-the-flying-hellfish/abraham_simpson/",
      "alt": "",
      "author": "1",
      "description": "",
      "caption": "",
      "name": "abraham_simpson",
      "status": "inherit",
      "uploaded_to": 3944,
      "date": "2021-11-15 10:11:31",
      "modified": "2021-11-15 10:11:31",
      "menu_order": 0,
      "mime_type": "image/webp",
      "type": "image",
      "subtype": "webp",
      "icon": "https://hellfish.media/wp-includes/images/media/default.png",
      "width": 302,
      "height": 482,
      "sizes": {
        "thumbnail": "https://hellfish.media/wp-content/uploads/2021/11/Abraham_Simpson-150x150.webp",
        "thumbnail-width": 150,
        "thumbnail-height": 150,
        "medium": "https://hellfish.media/wp-content/uploads/2021/11/Abraham_Simpson-188x300.webp",
        "medium-width": 188,
        "medium-height": 300,
        "medium_large": "https://hellfish.media/wp-content/uploads/2021/11/Abraham_Simpson.webp",
        "medium_large-width": 302,
        "medium_large-height": 482,
        "large": "https://hellfish.media/wp-content/uploads/2021/11/Abraham_Simpson.webp",
        "large-width": 302,
        "large-height": 482,
        "1536x1536": "https://hellfish.media/wp-content/uploads/2021/11/Abraham_Simpson.webp",
        "1536x1536-width": 302,
        "1536x1536-height": 482,
        "2048x2048": "https://hellfish.media/wp-content/uploads/2021/11/Abraham_Simpson.webp",
        "2048x2048-width": 302,
        "2048x2048-height": 482,
        "avatar": "https://hellfish.media/wp-content/uploads/2021/11/Abraham_Simpson.webp",
        "avatar-width": 302,
        "avatar-height": 482
      }
    }
  }
}
```

Additionally, if you want to default the format to standard for all response data, you can enforce this by using the `acf/settings/rest_api_format` filter:

```php php
add_filter( 'acf/settings/rest_api_format', function () {
    return 'standard';
} );
```

Should you want to apply specific additional formatting on a WP REST API ACF field value, the `acf/rest/format_value_for_rest` filter is applied on all ACF field values formatted for the WP REST API:

```php php
/**
     * Filter the formatted value for a given field.
     *
     * @param mixed      $value_formatted The formatted value.
     * @param string|int $post_id The post ID of the current object.
     * @param array      $field The field array.
     * @param mixed      $value The raw/unformatted value.
     * @param string     $format The format applied to the field value.
     */
    return apply_filters( 'acf/rest/format_value_for_rest', $value_formatted, $post_id, $field, $value, $format );
```

You can use this filter to apply your own formatting/output on the formatted field value. For example, implementing this code snippet will make every `acf` field value in the response include the field label as part of the field object:

```php php
add_filter('acf/rest/format_value_for_rest', function ($value_formatted, $post_id, $field, $value, $format){
    return array(
        $field['label'] => $value_formatted
    );
}, 10, 5);
```

```json php
{
  "acf": {
    "author": {
      "Author": "Abraham Simpson"
    },
    "author_bio": {
      "Author Bio": "<b>Abraham Jebediah \"Abe\" Simpson II</b>, commonly known as <b>Grampa Simpson</b> or simply <b>Grampa</b>, (born August 26, 1920) is a major character in <i><a title=\"The Simpsons\" href=\"https://simpsons.fandom.com/wiki/The_Simpsons\">The Simpsons</a></i>. He is the oldest patriarch of the <a title=\"Simpson family\" href=\"https://simpsons.fandom.com/wiki/Simpson_family\">Simpson family</a>, father of <a title=\"Homer Simpson\" href=\"https://simpsons.fandom.com/wiki/Homer_Simpson\">Homer Simpson</a>, and paternal grandfather of <a title=\"Bart Simpson\" href=\"https://simpsons.fandom.com/wiki/Bart_Simpson\">Bart</a>, <a title=\"Lisa Simpson\" href=\"https://simpsons.fandom.com/wiki/Lisa_Simpson\">Lisa</a> and <a title=\"Maggie Simpson\" href=\"https://simpsons.fandom.com/wiki/Maggie_Simpson\">Maggie Simpson</a>."
    },
    "author_image": {
      "Author Image": 3949
    }
  }
}
```

It is also possible to use this filter for specific field types, or on specific fields by name or key.

Apply to all fields of type `text`:

```php php
add_filter('acf/rest/format_value_for_rest/type=text', function ($value_formatted, $post_id, $field, $value, $format){
    // return the overridden value
}, 10, 5);
```

Apply to the field with the name `author`:

```php php
add_filter('acf/rest/format_value_for_rest/name=author', function ($value_formatted, $post_id, $field, $value, $format){
    // return the overridden value
}, 10, 5);
```

Apply to the field with the key `field_123456789`:

```php php
add_filter('acf/rest/format_value_for_rest/key=field_123456789', function ($value_formatted, $post_id, $field, $value, $format){
    // return the overridden value
}, 10, 5);
);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#filtering-the-fields-displayed-on-any-endpoint)

### Filtering the fields displayed on any endpoint

Link copied

The `acf/rest/get_fields` filter can be used to control which fields are shown or available for update. The `$http_method` parameter passed to the filter can be used to alter the fields displayed for a specific request method (i.e. GET, POST, or OPTIONS):

```php php
add_filter( 'acf/rest/get_fields', function ( $fields, $resource, $http_method ) {
    // Modify and return the $fields array here.

    // Example 1: Disable all fields for all request methods on a particular custom post type.
    if ( $resource['type'] == 'post' && $resource['sub_type'] == 'book' ) {
        return [];
    }

    // Example 2: Show only a specific field on term GET requests.
    if ( $http_method == 'GET' && $resource['type'] == 'term' ) {
        return wp_list_filter( $fields, [ 'name' => 'author' ] );
    }

    // Example 3: Exclude particular field types on user POST requests.
    if ( $http_method == 'POST' &&  $resource['type'] == 'user' ) {
        return array_filter( $fields, function ( $field ) {
            return ! in_array( $field['type'], [\
                'password',\
                'file',\
            ] );
        } );
    }

    return $fields;
}, 10, 3 );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#embed-links)

### Controlling the REST API embed links

Link copied

GET requests to objects with certain field types will also include an embed link – a URL which points to another resource. An example of this would be the User field, which will add a link to the selected user in the `_links` section of the REST response:

```json php
"acf:user": [\
  {\
    "embeddable": true,\
    "href": "https://hellfish.media/wp-json/wp/v2/users/1"\
  }\
],
```

If you need to simplify the REST response, it is possible to disable the embed link handler using the global `acf/settings/rest_api_embed_links` filter:

```php php
add_filter( 'acf/settings/rest_api_embed_links', '__return_false' );
```

If more granular control is required the `acf/rest/get_field_links` filter and its `type`, `name`, and `key` variations can be used to modify the links returned at the field level. e.g.;

```php php
add_filter( 'acf/rest/get_field_links', function ( $links, $post_id, $field, $value ) {
    // Returning an empty array or any value that loosely equates to FALSE will disable links for this particular field. e.g;
    if ( $field['name'] === 'author' ) {
        return false;
    }

    // Define any number of embeddable links and choose how to group them using the rel key. Note that if embeddable is
    // set to FALSE, the resource will not be expanded when the _embed query parameter is present.
    $links = [\
        [\
            'rel' => 'acf:post',\
            'href' => rest_url( 'wp/v2/posts/123' ),\
            'embeddable' => true,\
        ],\
        [\
            'rel' => 'acf:post',\
            'href' => rest_url( 'wp/v2/posts/456' ),\
            'embeddable' => true,\
        ],\
        [\
            'rel' => 'acf:user',\
            'href' => rest_url( 'wp/v2/users/234' ),\
            'embeddable' => true,\
        ],\
        [\
            'rel' => 'author_meta_group',\
            'href' => 'http://example.com', // External links can be used.\
            'embeddable' => false, // FALSE disables WordPress' embed handling.\
        ],\
    ];

    return $links;
}, 10, 4 );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#controlling-a-fields-schema)

### Controlling a field’s schema

Link copied

Schema is used by WordPress to validate and sanitize data on input. It also allows external systems/services to understand the API data. Schema is generated for each resource endpoint by ACF. It is possible to control a field’s schema using the `acf/rest/get_field_schema` filter and its `type`, `name`, and `key` variations. e.g.:

```php php
add_filter( 'acf/rest/get_field_schema', function ( $schema, $field ) {
    if($field['type'] === 'number'){
        $schema['minimum'] = 1;
        $schema['maximum'] = 100;
        $schema['multipleOf'] = 1;
    }

    return $schema;
}, 10, 2 );
```

For more information on extending the WP REST API, please see the [schema documentation](https://developer.wordpress.org/rest-api/extending-the-rest-api/schema/).

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#related)

## Related

Link copied

- Guides: [ACF Security Principles](https://www.advancedcustomfields.com/resources/acf-security-principles/)
- Getting Started: [Post Types and Taxonomies](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/)
- : [Frequently Asked Questions](https://www.advancedcustomfields.com/resources/frequently-asked-questions/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Videos: [Creating a Custom Taxonomy with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#)