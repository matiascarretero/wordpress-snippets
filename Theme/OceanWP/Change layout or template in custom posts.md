## Change layout / template in custom posts
You can override the layout of custom pages, post-types or archive with this hook. You must return: full-width, full-screen, left-sidebar, right-sidebar, both-sidebars, or default $class.

**Where to place this code?** 
your-child-theme/functions.php

```php
function io_ocean_post_layout_class( $class ) {
    if ( is_singular('page') || is_archive('page') ) { // i.e. it will set full-width layour for pages
        $class = 'full-width';
    }
    return $class;
}
add_filter( 'ocean_post_layout_class', 'io_ocean_post_layout_class', 20 );
```