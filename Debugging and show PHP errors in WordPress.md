## Debugging
WordPress hides PHP errors and warnings for default. You can temporaly enable error display with one of the following methods:

### A) Enable error reporting in every page
You should append this code in wp-config.php. Change variable $debug to "true" or "false" to enable/disable error reporting. Don't include braces.
```php
$debug = true;
if($debug) {
	define( 'WP_DEBUG', true );
	define( 'WP_DEBUG_DISPLAY', true );
	define( 'WP_DEBUG_LOG', true );
	ini_set('display_errors',1);
	ini_set('display_startup_errors',1);
	error_reporting(E_ALL);
} else {
	define('WP_DEBUG', false);
	ini_set('display_errors',0);
	ini_set('display_startup_errors',0);
	error_reporting(0);
}
```
### B) Enable error reporting in specific URLs
To debug specific URLs, you could append parameter enable_debug to the URL just like this: https://domain.com/?enable_debug=my_secret_key
```php 
if ( !empty( $_GET['enable_debug'] ) && $_GET['enable_debug'] === 'my_secret_key' ) { // Change 'my_secret_key' to something different
	define( 'WP_DEBUG', true );
	define( 'WP_DEBUG_DISPLAY', true );
	define( 'WP_DEBUG_LOG', true );
	ini_set('display_errors',1);
	ini_set('display_startup_errors',1);
	error_reporting(E_ALL);
} 
```