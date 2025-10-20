---
url: https://www.advancedcustomfields.com/resources/code-examples
scraped_at: 2025-10-20T02:17:00.206Z
---

# Code Examples

Last updated Jun 21, 2017

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#display-a-field)

## Display a field

Link copied

```php
<p><?php the_field('field_name'); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#retrieving-a-field-as-a-variable)

## Retrieving a field as a variable

Link copied

```php
<?php

$variable = get_field('field_name');

// do something with $variable

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#using-conditional-statements)

## Using conditional statements

Link copied

get\_field returns false if (value == “” \|\| value == null \|\| value == false)

```php
<?php

if(get_field('field_name'))
{
    echo '<p>' . get_field('field_name') . '</p>';
}

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#working-with-array-values)

## Working with Array values

Link copied

checkbox, select, relationship, repeater

```php
<?php

$values = get_field('field_name');
if($values)
{
    echo '<ul>';

    foreach($values as $value)
    {
        echo '<li>' . $value . '</li>';
    }

    echo '</ul>';
}

// always good to see exactly what you are working with
var_dump($values);

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#working-with-images--url)

## Working with Images – URL

Link copied

```php
<img src="<?php the_field('image_test'); ?>" alt="" />
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#working-with-images--id)

## Working with Images – ID

Link copied

By using the ID, you can retrieve any crop size of the image and even get the name of the file!

```php
<?php $image = wp_get_attachment_image_src(get_field('image_test'), 'full'); ?>
<img src="<?php echo $image[0]; ?>" alt="<?php echo get_the_title(get_field('image_test')) ?>" />
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#working-with-the-repeater-field)

## Working with the Repeater Field

Link copied

repeater can be accessed by get\_field or the\_repeater\_field / the\_sub\_field

```php
<?php if( have_rows('repeater_field_name') ): ?>

    <ul>

    <?php while( have_rows('repeater_field_name') ): the_row(); ?>

        <li>sub_field_1 = <?php the_sub_field('sub_field_1'); ?>, sub_field_2 = <?php the_sub_field('sub_field_2'); ?>, etc</li>

        <?php

        $sub_field_3 = get_sub_field('sub_field_3');

        // do something with $sub_field_3

        ?>

    <?php endwhile; ?>

    </ul>

<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#randomly-select-a-repeater-field-row)

## Randomly select a repeater field row

Link copied

```php
<?php

$rows = get_field('repeater_field_name');
$row_count = count($rows);
$i = rand(0, $row_count - 1);

echo $rows[ $i ]['sub_field_name'];

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#getting-values-from-another-page)

## Getting values from another page

Link copied

```php
<?php

$other_page = 12;

?>
<p><?php the_field('field_name', $other_page); ?></p>
<?php

// get variable
$variable = get_field('field_name', $other_page);

// repeater field: note that the_sub_field and get_sub_field don't need a post id parameter
if( have_rows('repeater_field_name', $other_page) ): ?>

    <ul>

    <?php while( have_rows('repeater_field_name', $other_page) ): the_row(); ?>

        <li>sub_field_1 = <?php the_sub_field('sub_field_1'); ?>, sub_field_2 = <?php the_sub_field('sub_field_2'); ?>, etc</li>

        <?php

        $sub_field_3 = get_sub_field('sub_field_3');

        // do something with $sub_field_3

        ?>

    <?php endwhile; ?>

    </ul>

<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#query-posts-with-acf-values)

## Query posts with ACF values

Link copied

Example of finding Events (post type) where location (custom field – select) equals Melbourne (value).
Lots to read here: http://codex.wordpress.org/Template\_Tags/get\_posts.

```php
<?php

$posts = get_posts(array(
    'numberposts' => -1,
    'post_type' => 'event',
    'meta_key' => 'location',
    'meta_value' => 'melbourne'
));

if($posts)
{
    echo '<ul>';

    foreach($posts as $post)
    {
        echo '<li><a href="' . get_permalink($post->ID) . '">' . get_the_title($post->ID) . '</a></li>';
    }

    echo '</ul>';
}

?>
```

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

[Link to heading#](https://www.advancedcustomfields.com/resources/code-examples/#related)

## Related

Link copied

- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Guides: [Get values from another post](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/)
- Guides: [Sort a Repeater Field](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/)
- Content: [Gallery](https://www.advancedcustomfields.com/resources/gallery/)
- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)

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

[Got it](https://www.advancedcustomfields.com/resources/code-examples/#)