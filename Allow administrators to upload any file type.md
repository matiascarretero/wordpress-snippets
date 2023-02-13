### Allow administrators to upload any file type
Paste this code in *wp-config.php*
- Just works for administrators.
- It is useful tu upload .svg files.
```php
define( 'ALLOW_UNFILTERED_UPLOADS', true );
```