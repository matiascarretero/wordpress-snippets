## Disable page header (title + breadcrumbs) in custom posts
You can disable title and breadcrumbs in custom pages with this filter. Return *false* to disable, or *true* to enable.

**Where to place this code?** 
your-child-theme/functions.php

```php
function io_ocean_display_page_header_heading( $return ) {
    if ( is_shop() ) { // i.e is will hide header in WooCommerce pages
        $return = false;
    }
    return $return;
 }
 add_filter(  'ocean_display_page_header_heading',  'io_ocean_display_page_header_heading'  );
```