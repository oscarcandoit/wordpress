---
url: https://www.advancedcustomfields.com/resources/google-map
scraped_at: 2025-10-20T02:33:17.433Z
---

# Google Map

Last updated Mar 27, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#description)

## Description

Link copied

The Google Map field provides an interactive map interface for selecting a location. This field type uses the Google Maps JS API to provide autocomplete searching, reverse geocoding lookup and an interactive marker.

**New** The Google Map field saves more location data in version 5.8.6!

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#screenshots)

## Screenshots

Link copied

[![a Google Map field displaying a sample map](https://www.advancedcustomfields.com/wp-content/uploads/2013/11/acf-google-map-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/11/acf-google-map-field-interface.png) The Google Map field interface[![List of field settings shown when setting up a Google Map field](https://www.advancedcustomfields.com/wp-content/uploads/2013/11/acf-google-map-field-settings.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/11/acf-google-map-field-settings.png) The Google Map field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#changelog)

## Changelog

Link copied

- Added more location data to the value in version 5.8.6.
- Added `acf/fields/google_map/api` filter in version 4.3.9

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#settings)

## Settings

Link copied

- **Center**


Defines the initial map center point latitude and longitude.

- **Zoom**


Sets the initial zoom level of the map.

- **Height**


Sets the height of the map.


[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#requirements)

## Requirements

Link copied

In order use of the Google Maps JavaScript API, you must first register a valid API key. To obtain an API key, please follow Google’s [Get an API Key](https://developers.google.com/maps/documentation/javascript/get-api-key) instructions. The Google Maps field requires the following APIs; Maps JavaScript API, Geocoding API and Places API.

As of March 1st, 2025, Google has deprecated the Places API used by the ACF Google Maps field. Existing sites using the Google Maps field should not be impacted, but new sites will have to enable the Legacy Places API, which can be done [here](https://console.cloud.google.com/apis/library/places-backend.googleapis.com). The Google Maps field will be updated to use the new Places API in a future release.

To register your Google API key, please use one of the following methods.

```php
// Method 1: Filter.
function my_acf_google_map_api( $api ){
    $api['key'] = 'xxx';
    return $api;
}
add_filter('acf/fields/google_map/api', 'my_acf_google_map_api');

// Method 2: Setting.
function my_acf_init() {
    acf_update_setting('google_api_key', 'xxx');
}
add_action('acf/init', 'my_acf_init');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#template-usage)

## Template usage

Link copied

The Google Map field returns an array of data for the selected location. The minimum data returned will include _address_, _lat_ and _lng_ values.

**New** Since version 5.8.6, the minimum data will also include the current _zoom_ level alongside optional data for _street\_number_, _street\_name_, _city_, _state_, _post\_code_ and _country_. Not all location results will return values for optional data keys, therefore it is important to first check if the data exists. Some optional data is also provided in a shortened format and is saved with a key suffix of “\_short”.

To display the saved location into a Google Map, please use the helper code.

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#google-maps-helper-code)

### Google Maps helper code

Link copied

The following code provides helper functionality to use in your project.

```php
<style type="text/css">
.acf-map {
    width: 100%;
    height: 400px;
    border: #ccc solid 1px;
    margin: 20px 0;
}

// Fixes potential theme css conflict.
.acf-map img {
   max-width: inherit !important;
}
</style>
<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=Function.prototype"></script>
<script type="text/javascript">
(function( $ ) {

/**
 * initMap
 *
 * Renders a Google Map onto the selected jQuery element
 *
 * @date    22/10/19
 * @since   5.8.6
 *
 * @param   jQuery $el The jQuery element.
 * @return  object The map instance.
 */
function initMap( $el ) {

    // Find marker elements within map.
    var $markers = $el.find('.marker');

    // Create gerenic map.
    var mapArgs = {
        zoom        : $el.data('zoom') || 16,
        mapTypeId   : google.maps.MapTypeId.ROADMAP
    };
    var map = new google.maps.Map( $el[0], mapArgs );

    // Add markers.
    map.markers = [];
    $markers.each(function(){
        initMarker( $(this), map );
    });

    // Center map based on markers.
    centerMap( map );

    // Return map instance.
    return map;
}

/**
 * initMarker
 *
 * Creates a marker for the given jQuery element and map.
 *
 * @date    22/10/19
 * @since   5.8.6
 *
 * @param   jQuery $el The jQuery element.
 * @param   object The map instance.
 * @return  object The marker instance.
 */
function initMarker( $marker, map ) {

    // Get position from marker.
    var lat = $marker.data('lat');
    var lng = $marker.data('lng');
    var latLng = {
        lat: parseFloat( lat ),
        lng: parseFloat( lng )
    };

    // Create marker instance.
    var marker = new google.maps.Marker({
        position : latLng,
        map: map
    });

    // Append to reference for later use.
    map.markers.push( marker );

    // If marker contains HTML, add it to an infoWindow.
    if( $marker.html() ){

        // Create info window.
        var infowindow = new google.maps.InfoWindow({
            content: $marker.html()
        });

        // Show info window when marker is clicked.
        google.maps.event.addListener(marker, 'click', function() {
            infowindow.open( map, marker );
        });
    }
}

/**
 * centerMap
 *
 * Centers the map showing all markers in view.
 *
 * @date    22/10/19
 * @since   5.8.6
 *
 * @param   object The map instance.
 * @return  void
 */
function centerMap( map ) {

    // Create map boundaries from all map markers.
    var bounds = new google.maps.LatLngBounds();
    map.markers.forEach(function( marker ){
        bounds.extend({
            lat: marker.position.lat(),
            lng: marker.position.lng()
        });
    });

    // Case: Single marker.
    if( map.markers.length == 1 ){
        map.setCenter( bounds.getCenter() );

    // Case: Multiple markers.
    } else{
        map.fitBounds( bounds );
    }
}

// Render maps on page load.
$(document).ready(function(){
    $('.acf-map').each(function(){
        var map = initMap( $(this) );
    });
});

})(jQuery);
</script>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#render-a-single-marker-onto-a-map)

### Render a single marker onto a map

Link copied

This example demonstrates how to display a Google Map field value on a map. Note the aforementioned Helper code is required to convert the HTML into an interactive map.

```php
<?php
$location = get_field('location');
if( $location ): ?>
    <div class="acf-map" data-zoom="16">
        <div class="marker" data-lat="<?php echo esc_attr($location['lat']); ?>" data-lng="<?php echo esc_attr($location['lng']); ?>"></div>
    </div>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#render-multiple-markers-onto-a-map)

### Render multiple markers onto a map

Link copied

This example demonstrates how to display multiple Google Map field values on the same map. In this example, a Repeater field is used to define a Title, Description and Location. Note the aforementioned Helper code is required to convert the HTML into an interactive map.

```php
<?php if( have_rows('locations') ): ?>
    <div class="acf-map" data-zoom="16">
        <?php while ( have_rows('locations') ) : the_row();

            // Load sub field values.
            $location = get_sub_field('location');
            $title = get_sub_field('title');
            $description = get_sub_field('description');
            ?>
            <div class="marker" data-lat="<?php echo esc_attr($location['lat']); ?>" data-lng="<?php echo esc_attr($location['lng']); ?>">
                <h3><?php echo esc_html( $title ); ?></h3>
                <p><em><?php echo esc_html( $location['address'] ); ?></em></p>
                <p><?php echo esc_html( $description ); ?></p>
            </div>
    <?php endwhile; ?>
    </div>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#display-location-address-details)

### Display location address details

Link copied

**New** This example demonstrates how to display location address details. These details can be found in a value saved since version 5.6.8.

```php
<?php
$location = get_field('location');
if( $location ) {

    // Loop over segments and construct HTML.
    $address = '';
    foreach( array('street_number', 'street_name', 'city', 'state', 'post_code', 'country') as $i => $k ) {
        if( isset( $location[ $k ] ) ) {
            $address .= sprintf( '<span class="segment-%s">%s</span>, ', $k, $location[ $k ] );
        }
    }

    // Trim trailing comma.
    $address = trim( $address, ', ' );

    // Display HTML.
    echo '<p>' . $address . '.</p>';
}
```

```php
<p>123, Foo Bar Street, Melbourne, Victoria, 3000, Australia.</p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#rendering-a-hidden-map)

### Rendering a hidden map

Link copied

Initializing a Google Map on a hidden element can lead to unexpected results when shown. To solve this problem, trigger a “resize” event on the map variable after the map element is visible.

```php
google.maps.event.trigger(map, 'resize');
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

[Link to heading#](https://www.advancedcustomfields.com/resources/google-map/#related)

## Related

Link copied

- Filters: [acf/fields/google\_map/api](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Choice: [Select](https://www.advancedcustomfields.com/resources/select/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)

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

[Got it](https://www.advancedcustomfields.com/resources/google-map/#)